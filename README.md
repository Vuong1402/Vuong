# Vuong lab8a
#include <iostream>
 bool is_same_color( const int  k, const int  &l,
                     const int  m, const int  &n,
                     bool  chess_board[], const int  &dim )
 {
   return  chess_board[ k*dim + l ] == chess_board[ m*dim + n ];
 }
 int  main()
 {
 
   int  k = 1;
   int  l = 1;
   int  m = 6;
   int  n = 5;
 
   const int dim = 8;
   bool  chess_board[ dim ][ dim ];
   bool  color = false;          
       for ( int  i = 0; i < dim; ++i )
       {
         color = !color;
             for ( int  j = 0; j < dim; ++j )
             {
                chess_board[i][j] = color;
                color = !color;
             }
       }
      for ( int  i = dim - 1; i >= 0; --i )
      {
             for ( int  j = 0; j < dim; ++j )
             {
                    if (    ( ( i == k ) && ( j == l ) )
                          ||
                            ( ( i == m ) && ( j == n ) )
                        )
                      std::cout << "X ";
                    else
                      std::cout << chess_board[i][j] << " ";
             }
        std::cout << "\n";
      }
 
   std::cout << "\nIs same color?: "
             << is_same_color( k, l, m, n, *chess_board, dim ) << "\n";
   return 0;
 }
