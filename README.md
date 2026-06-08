# Lloyd's Algorithm — K-Means Clustering Visualizer

A interactive, visually rich simulation of **Lloyd's Algorithm** (K-Means Clustering) built with vanilla HTML, CSS, and SVG/JS.

👉 **Live Demo:** [https://lloyds-algorithm.vercel.app](https://lloyds-algorithm.vercel.app)

---

## ⚡ Features

- **Interactive SVG Canvas**: Visualize clustering boundaries, data points, and centroids dynamically.
- **Adjustable Hyperparameters**:
  - **K (Clusters)**: Adjust the number of centroids between 2 and 6.
  - **Points**: Adjust the number of generated dataset points from 20 to 120.
  - **Speed**: Slow, 1×, and Fast simulation speeds.
- **Simulation Controls**:
  - **Step**: Execute one iteration of the algorithm (alternates between assignment and centroid updates).
  - **Run all**: Automatically run iterations until convergence.
  - **Reset**: Generate a new random dataset and place initial centroids using the Forgy method.
- **Metrics Dashboard**: Monitors Iteration count, WCSS (Within-Cluster Sum of Squares), and convergence status.
- **Mathematical Explanation Panel**: Highlights the current algorithm phase (Initialization, Assignment, Update, Convergence) with its mathematical formulation.
- **Dynamic Log**: A scrollable list tracking the detailed status of each step.

---

## 🔍 How Lloyd's Algorithm Works

Lloyd's Algorithm is a coordinate descent method used to partition $N$ data points into $K$ clusters:

1. **Initialization (Forgy method)**: Select $K$ random observations from the dataset as initial centroids:
   $$\mu_1, \mu_2, \dots, \mu_k \in \mathbb{R}^2$$
2. **Assignment (E-step)**: Assign each point $x_i$ to its nearest centroid based on squared Euclidean distance:
   $$C(i) = \text{argmin}_j \|x_i - \mu_j\|^2$$
3. **Centroid Update (M-step)**: Move each centroid to the mean of its assigned points:
   $$\mu_j \leftarrow \frac{1}{|S_j|} \sum_{x_i \in S_j} x_i$$
4. **Convergence**: Stop when the centroids no longer change position or the assignment is stable.

---

## 🛠️ Tech Stack

- **Core**: HTML5, Vanilla JavaScript (ES6+), SVG
- **Styling**: Vanilla CSS (Custom properties, dark mode theme)
- **Deployment**: [Vercel](https://vercel.com)

---

## 🚀 Running Locally

1. Clone this repository:
   ```bash
   git clone https://github.com/mo-ri-ch/lloyds-algorithm.git
   ```
2. Navigate to the project directory:
   ```bash
   cd lloyds-algorithm
   ```
3. Open `index.html` directly in your browser or run a simple local server:
   ```bash
   python -m http.server 8000
   ```
