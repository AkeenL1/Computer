If we use column oreinted storage, besides only loading the columns that are required for a given query, we can further reduce the demands on disk by compressing the data. One method is called bitmap encoding, which works in part because of the repetitive nature of data in a fact table.

The number of distinct values in a column - n - is usually quite small, we can now take a column with n distinct values & turn each into their own bitmap, giving us n bitmaps
I.E. if our column was [1,1,2,1,3] our bitmap for 1 would look like [1,1,0,1,0].

If n is small the bitmaps can be stored w/ one bit per row, but if n is larger there will be a lot of zeroes in most of the bitmaps (this is called a sparse bitmap), we can perform run-length encoding on these to further compress the data.

[[Memory bandwidth and vectorized processing]]