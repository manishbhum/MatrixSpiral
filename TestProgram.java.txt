import java.util.*;
public class TestProgram {

	public static void main(String[] args) {
		Scanner s= new Scanner(System.in);
		System.out.println("Please enter the number of rows");
		int rows= s.nextInt();

		System.out.println("Please enter the number of column");
		int column= s.nextInt();
		int [][] array= new int[rows][column];
		System.out.println("Please enter the values of array");
		for(int i= 0; i<rows;i++){
			for (int j=0;j<column;j++){
				array[i][j]=s.nextInt();
			}
		}
		printSquirral(rows,column,array);
	}
	
	private static void printSquirral(int rows, int column, int[][] array) {
		int startRow =0,startColumn=0;
		while(startRow <rows && startColumn < column){
			for(int i = startColumn; i<column;i++){
				System.out.print(array[startRow][i]+" ");
			}			
			startRow++;
			for(int i = startRow; i<rows;i++){
				System.out.print(array[i][column-1]+" ");
			}
			column--;

			if(startRow < rows){
				for(int i = column; i > startColumn;i--){
					System.out.print(array[rows-1][i-1]+" ");
				}
				
				rows--;
			}
			

			if(startColumn < column){
				for(int i = rows; i>startRow;i--){
					System.out.print(array[i-1][startColumn]+" ");
				}
				startColumn++;
			}
		}
	}

}