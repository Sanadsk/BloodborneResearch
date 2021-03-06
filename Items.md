# This is my research on how items are placed in maps, and how the MSB files are linked to the ItemLotParam.

First of all, the ItemLotParam contains many information about how items are placed into maps.
The main columns we will focus on are: ID / ItemLotId01 / ItemLotId02 / getItemFlagId

So to make this easier, I will showcase an example.

We will be using the Saw Hunter Badge which its item ID is 4110 (100E).
So if we go to that ID in the ItemLotParam, we can see that it has this information:
  
  **•ID: 2410290**
  
  **•ItemLotId01: 4110**
  
  **•ItemLotId02: 0**
  
  **•getItemFlagId: 52410290**
  
Now if you notice, the getItemFlagId is the same as ItemLotId01 but with an extra 5 at the beginning. This is normal for most of the items but there are some items that has it different. In that case, we use the getItemFlagId but we remove the 5.

Now we use the ID **(2410290)** and we convert it to HEX, which becomes **(24C732)**, but the way that the files read it is **32 C7 24 00**. So we use that ID and search through the MSB files, and the results show:

  **•m24_01_00_01.msb**
  
  **•m24_01_00_00.msb**
  
  **•m24_01_00_11.msb**
  
  These are the MSB files for Central Yharnam, where the Saw Hunter Badge is located.
