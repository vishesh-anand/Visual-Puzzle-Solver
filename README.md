# Visual Puzzle Solver
Project aims to solve puzzles like Sudoku, Rubik's Cube, etc visually using device camera. 
Currently, I can only solve Sudoku. But, it will be updated with Rubik's Cube and maybe Crossword

It is a preliminary version with an ability to solve sudoku under conditions of uniform light intensity and can recognise only printed digits. Sudoku is solved using *backtracking* algorithm

**PROCEDURE -** 
-   **Preprocessing steps :** Sudoku grid is pre-processed using -
	1.  Image converted to GRAYSCALE
    
	2.  Image blurring(Gaussian Blur) for noise-removal
    
	3.  Adaptive Thresholding for a much cleaner segmentation of image in case unequal light brightness
    
	4.  Erosion + Dilation
    

-   **Finding biggest contour**(findContours & drawContours) in the image and using it as Sudoku
    
-   Using **Warp Perspective** to zoom in to the Region Of Interest defined by Contour
    

-   Each cell of the grid is separated and stored using suitable contours.
    
-   The contour based cells are sorted in left-to-right and top-to-bottom manner
    
-   **Digit Identification:**
    

	Here, I have used my own pre-trained model for digit classification

-   The grid is stored in a 2d-array
    
-   The puzzle is solved using a *backtracking algorithm.*
    
-   The solution is stored in grid format and then overlaid on the initial image

