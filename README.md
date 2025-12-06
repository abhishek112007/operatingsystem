# CPU Scheduling Visualizer 🖥️⚡

A beautiful, interactive web application for visualizing and comparing CPU scheduling algorithms. Built with Next.js, React, and modern UI libraries.

![Next.js](https://img.shields.io/badge/Next.js-14.2.5-black)
![React](https://img.shields.io/badge/React-18-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4-38bdf8)

---

## ✨ Features

- 🎨 **Beautiful UI** - Modern gradient designs with smooth animations
- 📊 **6 Scheduling Algorithms** - Complete implementations with visualizations
- 📈 **Interactive Gantt Charts** - Color-coded process execution timeline
- 📉 **Performance Comparison** - Compare algorithms side-by-side
- 📄 **PDF Export** - Generate comprehensive reports
- 🎯 **Real-time Metrics** - Average turnaround time and waiting time
- 💫 **Smooth Animations** - Powered by Framer Motion and GSAP
- 📱 **Responsive Design** - Works on desktop, tablet, and mobile

---

## 🧮 Supported Algorithms

### 1. **FCFS (First Come First Serve)**
**Type**: Non-Preemptive

**How it works**:
- Processes are executed in the order they arrive in the ready queue
- The CPU is allocated to the process that arrives first
- Once a process starts execution, it runs to completion without interruption
- Simple to understand and implement

**Advantages**:
- ✅ Simple and easy to implement
- ✅ Fair in the sense of first-come, first-served
- ✅ No starvation - every process gets a chance

**Disadvantages**:
- ❌ Convoy Effect - short processes wait for long processes
- ❌ Poor average waiting time
- ❌ Not suitable for time-sharing systems

**Use Cases**:
- Batch processing systems
- Non-interactive systems where fairness is more important than efficiency

---

### 2. **SJF Non-Preemptive (Shortest Job First)**
**Type**: Non-Preemptive

**How it works**:
- Selects the process with the smallest burst time from the ready queue
- Once a process starts, it runs to completion
- If two processes have the same burst time, FCFS is used as a tiebreaker

**Advantages**:
- ✅ Optimal average waiting time
- ✅ Minimizes average waiting time for a given set of processes
- ✅ Better throughput than FCFS

**Disadvantages**:
- ❌ Starvation - long processes may wait indefinitely
- ❌ Difficult to predict burst time in practice
- ❌ Not suitable for interactive systems

**Use Cases**:
- Batch systems where job lengths are known
- Systems with predictable workloads

---

### 3. **SJF Preemptive (SRTF - Shortest Remaining Time First)**
**Type**: Preemptive

**How it works**:
- Always executes the process with the shortest remaining time
- When a new process arrives, compare its burst time with the remaining time of the current process
- If the new process has a shorter time, preempt the current process
- Also known as Shortest Remaining Time First (SRTF)

**Advantages**:
- ✅ Optimal - gives minimum average waiting time
- ✅ Better response time for short processes
- ✅ More efficient than non-preemptive SJF

**Disadvantages**:
- ❌ High context switching overhead
- ❌ Starvation for longer processes
- ❌ Requires knowledge of burst time

**Use Cases**:
- Real-time systems with known task durations
- Systems prioritizing quick turnaround for short tasks

---

### 4. **Priority Scheduling (Non-Preemptive)**
**Type**: Non-Preemptive

**How it works**:
- Each process is assigned a priority number (lower number = higher priority)
- CPU is allocated to the process with the highest priority
- Once a process starts, it runs to completion
- Equal priority processes are scheduled using FCFS

**Advantages**:
- ✅ Important processes can be prioritized
- ✅ Flexible - priorities can be assigned based on various criteria
- ✅ Good for systems with varying task importance

**Disadvantages**:
- ❌ Starvation - low priority processes may never execute
- ❌ Priority inversion problem
- ❌ Requires careful priority assignment

**Use Cases**:
- Operating systems kernel processes
- Systems with clearly defined task priorities
- Real-time systems with deadline requirements

---

### 5. **Priority Scheduling (Preemptive)**
**Type**: Preemptive

**How it works**:
- Similar to non-preemptive priority scheduling
- When a new process with higher priority arrives, it preempts the current process
- Current process is moved back to the ready queue
- Highest priority process always gets the CPU

**Advantages**:
- ✅ High priority processes get immediate attention
- ✅ Better response time for critical tasks
- ✅ More flexible than non-preemptive version

**Disadvantages**:
- ❌ Severe starvation for low priority processes
- ❌ High context switching overhead
- ❌ Priority inversion can be more problematic

**Solution to Starvation**: Aging - gradually increase priority of waiting processes

**Use Cases**:
- Real-time operating systems
- Systems with interrupt-driven tasks
- Emergency response systems

---

### 6. **Round Robin (RR)**
**Type**: Preemptive

**How it works**:
- Each process gets a fixed time slice (time quantum) to execute
- After time quantum expires, process is preempted and moved to the end of the ready queue
- CPU scheduler picks the next process from the queue
- Continues until all processes complete

**Time Quantum Selection**:
- **Too large**: Becomes FCFS (poor response time)
- **Too small**: High context switching overhead
- **Optimal**: Balance between response time and overhead (typically 10-100ms)

**Advantages**:
- ✅ Fair allocation of CPU time
- ✅ No starvation - every process gets CPU time
- ✅ Good response time for interactive systems
- ✅ Better for time-sharing systems

**Disadvantages**:
- ❌ Higher average turnaround time than SJF
- ❌ Context switching overhead
- ❌ Performance depends on time quantum selection

**Use Cases**:
- Time-sharing systems
- Interactive operating systems (Windows, Linux, macOS)
- Multi-user systems

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 20.x or higher
- **npm** or **yarn** package manager

### Installation

1. **Clone the repository**:
```bash
git clone https://github.com/yourusername/CPU-Scheduling-Visualizer.git
cd CPU-Scheduling-Visualizer
```

2. **Install dependencies**:
```bash
npm install
```

3. **Run the development server**:
```bash
npm run dev
```

4. **Open in browser**:
```
http://localhost:3000
```

### Build for Production

```bash
npm run build
npm start
```

---

## 📖 How to Use

### Step 1: Select Algorithm
- Choose from 6 available scheduling algorithms from the dropdown

### Step 2: Add Processes
- **Arrival Time**: When the process arrives in the ready queue
- **Burst Time**: CPU time required by the process
- **Priority**: Required for priority scheduling algorithms (lower number = higher priority)
- **Time Quantum**: Required for Round Robin (typically 2-4 units)

### Step 3: Run Simulation
- Click **"Run Algorithm"** button
- View the animated Gantt chart
- Check the output process table with metrics
- Review average turnaround time and waiting time

### Step 4: Compare Algorithms
- Click **"Compare Similar Algorithms"** to see performance differences
- Comparison automatically runs after executing an algorithm
- View line charts comparing ATT and AWT

### Step 5: Export Results
- Click **"Export Results"** to download a PDF report
- Report includes all tables, charts, and metrics

---

## 📊 Understanding the Metrics

### **Completion Time (CT)**
Time at which a process completes its execution
```
CT = Time when process finishes
```

### **Turnaround Time (TAT)**
Total time taken from arrival to completion
```
TAT = Completion Time - Arrival Time
```

### **Waiting Time (WT)**
Total time a process waits in the ready queue
```
WT = Turnaround Time - Burst Time
```

### **Average Turnaround Time (ATT)**
```
ATT = (Sum of all TAT) / Number of processes
```

### **Average Waiting Time (AWT)**
```
AWT = (Sum of all WT) / Number of processes
```

---

## 🛠️ Tech Stack

### **Frontend**
- **Next.js 14.2.5** - React framework with App Router
- **React 18** - UI library
- **TypeScript** - Type safety
- **TailwindCSS** - Utility-first CSS
- **Framer Motion** - Animation library
- **GSAP** - Advanced animations

### **UI Components**
- **Radix UI** - Headless component library
- **shadcn/ui** - Pre-built components
- **Lucide React** - Icon system
- **Recharts** - Chart library

### **State Management**
- **Recoil** - Global state management

### **Export**
- **jsPDF** - PDF generation
- **jsPDF-AutoTable** - Table generation in PDFs

### **API**
- **Next.js API Routes** - Backend endpoints
- **Axios** - HTTP client

---

## 📁 Project Structure

```
CPU-Scheduling-Visualizer/
├── app/
│   ├── (components)/          # React components
│   │   ├── ganttChart.tsx     # Gantt chart visualization
│   │   ├── inputProcessTable.tsx
│   │   ├── lineChart.tsx      # Comparison charts
│   │   ├── outputProcessTable.tsx
│   │   ├── processInserter.tsx
│   │   └── selectAlgorithm.tsx
│   ├── (lib)/                 # Utilities
│   │   └── recoilContextProvider.tsx
│   ├── (recoil)/              # State management
│   │   └── store.ts           # Global state atoms
│   ├── algorithms/
│   │   ├── metadata.ts        # Algorithm metadata
│   │   └── page.tsx           # Main algorithm page
│   ├── api/                   # Backend API routes
│   │   ├── fcfs/
│   │   │   ├── fcfs.js        # FCFS algorithm
│   │   │   └── route.tsx
│   │   ├── sjf_non_preemptive/
│   │   │   ├── sjf_non_preemptive.js
│   │   │   └── route.tsx
│   │   ├── sjf_preemptive/
│   │   │   ├── sjf_preemptive.js
│   │   │   └── route.tsx
│   │   ├── priority_non_preemptive/
│   │   │   ├── priority_non_preemptive.js
│   │   │   └── route.ts
│   │   ├── priority_preemptive/
│   │   │   ├── priority_preemptive.js
│   │   │   └── route.ts
│   │   └── round_robin/
│   │       ├── round_robin.js
│   │       └── route.ts
│   ├── globals.css            # Global styles
│   ├── layout.tsx             # Root layout
│   └── page.tsx               # Home page (redirects to /algorithms)
├── components/
│   └── ui/                    # Reusable UI components
├── lib/
│   └── utils.ts               # Utility functions
├── public/                    # Static assets
├── next.config.js             # Next.js configuration
├── tailwind.config.ts         # Tailwind configuration
├── tsconfig.json              # TypeScript configuration
└── package.json               # Dependencies
```

---

## 🎨 Color-Coded Gantt Chart

Each process is assigned a unique gradient color:
- **P0**: Blue gradient
- **P1**: Purple gradient
- **P2**: Pink gradient
- **P3**: Rose gradient
- **P4**: Orange gradient
- **P5**: Amber gradient
- **P6**: Lime gradient
- **P7**: Emerald gradient
- **P8**: Teal gradient
- **P9**: Cyan gradient
- **P10+**: Colors cycle through the palette

**Idle Time**: Gray gradient

---

## 🎯 Key Features Explained

### **Auto-Refresh Comparison**
After running any algorithm, the comparison chart automatically updates, eliminating the need to manually click "Compare Similar Algorithms".

### **Empty States**
Beautiful placeholder messages when:
- No algorithm is selected
- No processes are added
- No output is generated

### **Loading States**
Visual feedback with spinner animation during algorithm execution.

### **Error Handling**
Clear error messages displayed to users when something goes wrong.

### **Responsive Design**
- Desktop: Full layout with side-by-side panels
- Tablet: Stacked layout with horizontal scrolling
- Mobile: Vertical stacking with touch-friendly controls

---

## 🧪 Example Use Cases

### **For Students**
- Learn how different scheduling algorithms work
- Compare algorithm performance
- Prepare for OS exams and interviews
- Visualize concepts with animations

### **For Educators**
- Demonstrate scheduling algorithms in class
- Generate examples for assignments
- Show real-time comparisons
- Export results for presentations

### **For Developers**
- Understand OS scheduling internals
- Test edge cases
- Analyze algorithm behavior
- Study performance metrics

---

## 📚 Algorithm Comparison

| Algorithm | Type | Avg WT | Starvation | Context Switch | Use Case |
|-----------|------|--------|------------|----------------|----------|
| FCFS | Non-Preemptive | High | No | Low | Batch systems |
| SJF (NP) | Non-Preemptive | Optimal | Yes | Low | Predictable workloads |
| SJF (P) | Preemptive | Optimal | Yes | High | Short task priority |
| Priority (NP) | Non-Preemptive | Varies | Yes | Low | Fixed priorities |
| Priority (P) | Preemptive | Varies | Yes | Very High | Real-time systems |
| Round Robin | Preemptive | Medium | No | High | Time-sharing systems |

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit your changes**: `git commit -m 'Add amazing feature'`
4. **Push to the branch**: `git push origin feature/amazing-feature`
5. **Open a Pull Request**

---

## 📝 License

This project is open source and available under the MIT License.

---

## 🙏 Acknowledgments

- Built with [Next.js](https://nextjs.org/)
- UI components from [shadcn/ui](https://ui.shadcn.com/)
- Icons from [Lucide](https://lucide.dev/)
- Animations by [Framer Motion](https://www.framer.com/motion/)

---

## 📧 Contact

For questions, suggestions, or feedback:
- Open an issue on GitHub
- Create a pull request
- Star the repository if you find it helpful! ⭐

---

**Made with ❤️ for students learning Operating Systems**
