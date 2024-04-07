const DWORD dwWhiteToColorRet = 0x008D03BB;  <----- Return address so the function can continue its path

//Format
_declspec(naked) void WhiteColorChange_CodeCave()  <------- Function name
{
	_asm {

		push 0xFFFF8000          //Pushing the color
		push 12            
		push ecx

		jmp dwWhiteToColorRet   //Jumping back to the return address so i can continue the function
	}
}

//Hook For White Chat Color Change.
CodeCave(*==FUNCTION NAME==*, ==*ADDRESS TO EDIT*==, ==*NUMBER OF BYTES MOVED*==)

CodeCave(WhiteColorChange_CodeCave, 0x008D03B6, 5);



Also note that some of the addresses in this document require a codecave to access more than 5 bytes, you can use this codecave as an example to increase byte size in most functions.


