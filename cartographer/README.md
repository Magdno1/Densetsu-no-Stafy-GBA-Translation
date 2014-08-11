To correctly format the dumped script for reinsertion you will need to add this to the top of the file

// Define a TABLE
#VAR(Table, TABLE)
#VAR(engTable, TABLE)

// Load and activate the table
#ADDTBL("script/stafy.tbl", Table)
#ADDTBL("script/english.tbl", engTable)
#ACTIVETBL(Table)

// Setup GBA pointers and Pointer Table
#VAR(GBA, CUSTOMPOINTER)
// Create our pointer type
#CREATEPTR(GBA, "LINEAR", $-08000000, 32)


You will also need to give it an address to place the inserted text for example 0x00700000 would be:
#JMP($700000)


Finally do a search and replace on all "#W32(" and replace them with "#WRITE(GBA," now they should be ready for reinsertion.