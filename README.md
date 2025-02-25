# This project is an example of using Win32 API DialogBoxParam.
### Enveironment: Visual Studio Pro 2017, Windows10 x64.

1. The mechanism of modal windows  
    The dialog box created by "DialogBox" family (such as DialogBox, DialogBoxIndirect, DialogBoxParam and DialogBoxIndirectParam) is a modal window. Before creation, the system will disable its parent window. And create a new message loop for it in these API functions. These functions also require a callback function (such as DialogProc) to process message. In other words, the modal dialog window has its own message loop and window procedure different from the main thread. Before the user click button such as "OK", "Cancel" or "Close", they are always in modal window message loop. After the buttons clicked, use "EndDialog" to return to the main message loop in the main thread. The parent window can respond again.
2. The mechanism of modaless windows  
    The dialog box created by "CreateDialog" family (such as CreateDialog, CreateDialogIndirect, CreateDialogParam and CreateDialogIndirectParam) is a modaless window. They will return after creation instead of creating a new message loop. The dialog box uses the message loop in the main thread. Therefore, the parent window can also resapond.
Added a github workflow and I now want to test it.
