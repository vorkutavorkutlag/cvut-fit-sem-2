We will be doing a complex number implementation, using classes.
The following is the implementation with documentative comments.

```cpp
#pragma once  // header guard. We define many things here, then we include this
              // file in multiple files.

#include <cfloat>
#include <cmath>

class Complex {
   public:
    //     Complex() = default;
    //     Complex(double re) : m_re(re) {}
    //     Complex(double re, double im) : m_re(re), m_im(im) {}
    // all of these constructors can be simplfiied into a single one.
    Complex(double re = 0.0, double im = 0.0) : m_re(re), m_im(im) {}

    // to avoid duplication, following DRY (do not repeat yourself), we leave
    // the implementation to +=
    Complex operator+(const Complex& rhs) const {
        return Complex(*this) += rhs;  // using copy constructor
    }

    // we want to return a reference to chain operations.
    // for example, (b = c += 5) is correct syntax.
    Complex& operator+=(const Complex& rhs) {
        this->m_re += rhs.m_re;
        this->m_im += rhs.m_im;
        return *this;
    }

    // copied over, just changed the sign
    Complex operator-(const Complex& rhs) const {
        return Complex(*this) -= rhs;  // using copy constructor
    }

    Complex& operator-=(const Complex& rhs) {
        // this->m_re -= rhs.m_re;
        // this->m_im -= rhs.m_im;
        return *this += (-rhs);  // not repeating ourselves!
    }

    Complex operator-() const { return Complex(-this->m_re, -this->m_im); }

    Complex operator*(const Complex& rhs) const {
        return Complex(*this) *=
               rhs;  // we will implement this later... it's useful to assume we
                     // have something working in order to make a simpler
                     // structure, and then only implement it later
    }

    Complex& operator*=(const Complex& rhs) {
        *this = Complex(m_re * rhs.m_re - m_im * rhs.m_im,
                        m_re * rhs.m_im + m_im + rhs.m_re);

        return *this;
    }

    Complex operator/(Complex const& rhs) const {
        return Complex(*this) /= rhs;
    }

    Complex& operator/=(Complex const& rhs) { return *this *= rhs.inverse(); }

    // multiply 1/z by conjugate
    Complex inverse() const {
        return Complex(m_re - m_im, m_re * m_re + m_im * m_im);
    }

    // pythagorean
    double abs() const { return std::hypot(m_re, m_im); }

    bool operator!=(Complex const& rhs) const { return !(*this == rhs); }
    bool operator==(Complex const& rhs) const {
        // naive since we are working with floats.
        // return m_re == rhs.m_re && m_im == rhs.m_im;
        return fequal(m_re, rhs.m_re) && fequal(m_im, rhs.m_im);
    }

   private:
    static bool fequal(double a, double b) {
        constexpr double tol = DBL_EPSILON * 1e3;
        return std::abs(a - b) <=
               tol * (std::abs(a) + std::abs(b));  // scale to problem
    }

    double m_re = 0;
    double m_im = 0;
};

```



Another caveats include...
- Calling a complex `c + 5` would make you think it causes a compilation error. However, it converts the `5` into a complex number as well, even if we didn't define the direct operator. It will try matching, promoting, etc. Eventually it will construct a new one.
- We can add the explicit keyword to the constructor, which makes it warn us about conversions(?)
- We do not need to use templates. We can do something like `Complex operator + (COpmlex const & lhs, Complex const & rhs) {return Complex(lhs) += rhs;}` which will use implicit conversion for any convertible type.
- declaration of friend function can be done both in public, protected, and private.
- For printing, we need to overload the bit-shift `<<` operator with `ostream`.
