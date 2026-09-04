# Sudoku Game & Solver Application (Android, IOS, Desktop)

## 1. Description
**Sudoku App** is a feature-rich, cross-platform Sudoku puzzle game and solver application built using Kotlin Multiplatform (KMP) and Compose Multiplatform. Cross-compiling for Android, iOS, and Desktop (JVM), sudokuapp offers interactive puzzle solving, automatic puzzle generation across difficulty levels, step-by-step algorithmic solving visualization, victory animations, and extensive automated test suites.

---

## 2. Technical Special Aspects
- **Backtracking Solver & Generator Engine**:
  - **`SudokuGenerator`**: Generates unique, solvable 9x9 Sudoku puzzles with symmetric clue removal across Easy, Medium, Hard, and Expert difficulties.
  - **`SudokuSolver`**: Implements a constraint-satisfaction backtracking algorithm capable of instant solutions or step-by-step visual solving transitions (`SudokuSolverScreenViewModel`).
- **Rich Composable UI Architecture**:
  - `SudokuBoard`: Touch-responsive 9x9 cell grid with highlight states for selected cells, rows, columns, and matching numbers.
  - `Confetti`: Custom canvas-rendered particle confetti animation for game completion.
  - `CustomOverlayScene`: Transition scene overlay architecture for victory/defeat dialogs (`GameWonDialogScreen`, `GameOverDialogScreen`).
- **Comprehensive Testing Infrastructure (`common-test-utils`)**:
  - Dedicated multiplatform testing module featuring custom dispatcher rules (`MainDispatcherRule`), Robolectric host integration, Turbine reactive flow testing, and headless video-recording UI test runners (`SudokuSolverScreenVideoTest`).
  - Microbenchmarking suite (`benchmark` module) evaluating solver algorithm execution times.

---

## 3. Technologies Used
- **Languages**: Kotlin (100% Shared UI & Business Logic)
- **UI Framework**: Compose Multiplatform (Android, iOS, Desktop)
- **Navigation**: Jetpack Navigation 3 
- **Dependency Injection**: Koin Compiler Plugin (`CoreModule`, `NavigationModule`, etc.,)
- **State & Concurrency**: Kotlin Coroutines, StateFlow, ViewModel
- **Build Infrastructure**: Gradle KTS Multi-Module (`shared`, `androidApp`, `desktopApp`, `iosApp`, `common-test-utils`, `androidUiTest`, `benchmark`)

---

## 4. Testing Technologies
- **Unit & Logic Testing**: `kotlin.test`, JUnit 5
- **Flow & Reactive Testing**: Turbine (`TurbineFlowTest`)
- **Android Host & UI Testing**: Robolectric (`RobolectricTest`), AndroidX Test (`androidUiTest`)
- **Visual & Video Testing**: Headless video recording test runners (`SudokuSolverScreenVideoTest`)
- **Performance Benchmarking**: AndroidX Benchmark library (`benchmark`)

---

## 5. Cloud Technologies
- N/A (Standalone cross-platform game application).

---

## 6. ROADMAP
- [ ] Implement camera OCR scanner to scan physical paper Sudoku puzzles into the app using computer vision.
- [ ] Add candidate digit "pencil marking" mode for manual puzzle solving.
- [ ] Introduce Daily Challenge puzzles with online cloud backup and streak statistics.
- [ ] Support puzzle variants including 6x6 Mini Sudoku, 16x16 Hexadoku, and Samurai Sudoku.
