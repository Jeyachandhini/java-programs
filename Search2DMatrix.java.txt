class Search2DMatrix{
    public boolean searchMatrix(int[][] matrix, int target) {
        if(matrix==null || matrix.length==0)
        {
            return false;
        }
        else
        {
            int row=matrix.length,col=matrix[0].length;
            for(int i=0;i<row;i++)
            {
                for(int j=0;j<col;j++)
                {
                  if(matrix[i][j]==target)
                  {
                      return true;
                  }
                  else if(matrix[i][j]>target)
                  {
                      col=j;
                  }
                }
             }
             return false;
        }  
    }
}