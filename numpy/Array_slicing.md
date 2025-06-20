array slilicing [:,0]  for ":" first value zero is defult and for last end is default. basicallly get all elements of arrrany. example
arr= [1,2],[2,3]... : arr= [1,2],[2,3]
and with ",0" arr=[1,2] means get elements on 0th means 1st coloumn...

[:,0]  all rows. 0th column . arr=[1,2]
[0,:] all columns. 0th row. arr=[1,2]
[1:,0] from 1st row, oly 0th column
[:] all ,or whole shit

                 
                 "xSorted = pts[np.argsort(pts[:, 0]), :]" 

