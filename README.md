# Riemann Sum Visualizer

An interactive, browser-based tool for visualising how Riemann sums approximate definite integrals. Built for classroom use in introductory calculus, quantitative methods, and microeconomics courses.

**Live demo:** [https://sakibanwar.github.io/riemannSum/](https://sakibanwar.github.io/riemannSum/)

![HTML](https://img.shields.io/badge/Built%20with-HTML%2FJS%2FCanvas-orange)
![License](https://img.shields.io/badge/License-Open-green)
![GitHub Pages](https://img.shields.io/badge/Hosted%20on-GitHub%20Pages-blue)


## What Is This?

This is a single-page interactive application that lets students explore the connection between rectangular approximation and definite integration. Users can select a function, adjust the number of rectangles, choose an approximation method (left, midpoint, or right), and watch in real time as the approximate area converges to the exact integral.

The tool includes both **pure mathematics functions** and **economics applications** (consumer and producer surplus), making it suitable for teaching across disciplines.


## Features

**Core functionality**
- Five built-in functions: $f(x) = x^2$, a cubic, a square root, and demand/supply curves for consumer and producer surplus
- Three Riemann sum methods: left endpoint, midpoint, and right endpoint
- Adjustable number of rectangles from 1 to 200 via a slider
- Custom integration limits (a, b) with real-time updates
- Animated convergence: a "Take to Limit" button that progressively increases the number of rectangles, visually demonstrating convergence to the exact area

**Visual and numerical feedback**
- Colour-coded rectangles overlaid on the function curve
- Live display of approximate area, exact integral, and absolute error
- Dotted vertical lines marking the integration bounds
- Dynamic axis scaling and gridlines

**Economics mode**
- Consumer surplus: area between the demand curve $P = 10 - 0.2x^2$ and a fixed price line at $P = 5$
- Producer surplus: area between the supply curve $P = 0.2x^2$ and the same price line
- Rectangles automatically adjust to measure the surplus region (between curve and price line) rather than the area under the curve


## Using This as a Teaching Tool

### Introductory Calculus / Quantitative Methods

**Concept: From rectangles to integrals.** Start with $f(x) = x^2$ on $[0, 4]$ using left endpoint rectangles. Set $n = 4$ and ask students to calculate the approximate area by hand ($\Delta x = 1$, heights at $x = 0, 1, 2, 3$). Then compare their hand calculation with the tool's output. Gradually increase $n$ and ask: *What happens to the error? Why?*

**Concept: Left vs. right vs. midpoint.** With $n$ fixed at a small number (say 5 or 10), toggle between the three methods. Ask students to predict which method overestimates and which underestimates for an increasing function, then verify visually.

**Concept: Taking the limit.** Use the "Take to Limit" animation to show that as $n \to \infty$, all three methods converge to the same value. This provides a concrete, visual anchor for the formal definition of the definite integral as a limit of Riemann sums.

**Concept: Changing bounds.** Adjust the start and end values to illustrate properties of definite integrals, such as $\int_a^b f(x)\,dx + \int_b^c f(x)\,dx = \int_a^c f(x)\,dx$.

### Microeconomics / Principles of Economics

**Concept: Consumer and producer surplus as areas.** Select the consumer surplus function. Explain that the shaded region between the demand curve and the price line represents the total benefit consumers receive from paying less than their willingness to pay. Use a small number of rectangles to make the "stacking" intuition concrete, then animate to show the exact surplus.

**Concept: Approximation in applied settings.** Point out that in practice, economists often work with discrete data (e.g., survey responses, market transactions at specific quantities). Riemann sums with a finite $n$ can be framed as a natural approximation when continuous demand/supply data is unavailable.

### Suggested Classroom Activities

1. **Predict and verify.** Before showing the tool, ask students to sketch rectangles by hand for $f(x) = x^2$ on $[0, 2]$ with $n = 4$ using left endpoints. Then display the tool and check their answers.
2. **Error analysis.** Have students record the error for $n = 5, 10, 25, 50, 100, 200$ and plot error against $n$. Ask them to describe the relationship. (This can be extended into a discussion of convergence rates.)
3. **Method comparison.** For the cubic function, ask students to determine which method (left, mid, right) gives the best approximation at $n = 10$ and explain why.
4. **Surplus estimation.** In an economics class, ask students to estimate consumer surplus using 5 rectangles by hand, then verify with the tool. Discuss why the approximation improves with more rectangles.
5. **Exit ticket.** After a lecture on definite integrals, use as a quick formative check: "Set $n = 3$ with right endpoints for $f(x) = 2\sqrt{x}$ on $[0, 9]$. What approximate area does the tool give? Is it an overestimate or underestimate?"


## How to Run Locally

Clone the repository and open `index.html` in any modern browser. No dependencies, no build step.

```bash
git clone https://github.com/sakibanwar/riemannSum.git
cd riemannSum
open index.html    # macOS
# or
xdg-open index.html  # Linux
# or simply double-click the file in your file manager
```

The tool runs entirely client-side using vanilla JavaScript and the HTML5 Canvas API. The only external dependency is Tailwind CSS (loaded via CDN for styling).


## Technical Details

The application is a single `index.html` file containing all HTML, CSS, and JavaScript. Key implementation details:

- **Rendering:** All graphics are drawn on an HTML5 `<canvas>` element using the 2D rendering context. The canvas automatically scales for high-DPI (Retina) displays.
- **Coordinate mapping:** A fixed viewport is defined for each function (independent of the integration limits), so the visual scale remains stable as users adjust the bounds.
- **Animation:** The "Take to Limit" feature uses `requestAnimationFrame` to increment $n$ smoothly from its current value up to 200, with acceleration at higher values.
- **Exact integrals:** Closed-form antiderivatives are hard-coded for each function to compute exact areas for comparison.


## Contributing

Suggestions, bug reports, and pull requests are welcome. If you use this tool in your teaching and have ideas for additional functions or features (e.g., trapezoidal rule, Simpson's rule, additional economics applications), please open an issue.


## Author

**Sakib Anwar**
Lecturer in Economics, University of Winchester
[sakibanwar.com](https://sakibanwar.com) | [GitHub](https://github.com/sakibanwar)


Link : https://sakibanwar.github.io/riemannSum/
