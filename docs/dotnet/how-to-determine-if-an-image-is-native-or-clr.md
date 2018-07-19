---
title: 'Vorgehensweise: bestimmen, ob ein Bild systemeigen oder CLR ist | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common language runtime, image testing
- images [C++], CLR verification
- /clr compiler option [C++], detecting use in compilation
- common language runtime, /clr compiler option
ms.assetid: 5a854822-6172-4b22-b236-320165412568
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 71b13c1f82f233589102c72ed08a731db7de5c56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128224"
---
# <a name="how-to-determine-if-an-image-is-native-or-clr"></a>Gewusst wie: Ermitteln, ob ein Bild systemeigen oder CLR ist
Eine Möglichkeit, um zu bestimmen, ob ein Image erstellt wurde, für die common Language Runtime ist die Verwendung **Dumpbin**[CLRHEADER](../build/reference/clrheader.md).  
  
 Sie können auch programmgesteuert überprüfen, ob ein Bild für die common Language Runtime erstellt wurde. Weitere Informationen finden Sie unter [wie: Erkennen von/CLR-Kompilierung](../dotnet/how-to-detect-clr-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird bestimmt, ob ein Image erstellt wurde, auf die common Language Runtime ausgeführt.  
  
```  
// detect_image_type.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
enum class CompilationMode {Invalid, Native, CLR };  
  
static CompilationMode IsManaged(String^ filename) {  
   try {  
      array<Byte>^ data = gcnew array<Byte>(4096);  
      FileInfo^ file = gcnew FileInfo(filename);  
      Stream^ fin = file->Open(FileMode::Open, FileAccess::Read);  
      Int32 iRead = fin->Read(data, 0, 4096);  
      fin->Close();  
  
      // Verify this is a executable/dll  
      if ((data[1] << 8 | data[0]) != 0x5a4d)  
         return CompilationMode::Invalid;  
  
      // This will get the address for the WinNT header  
      Int32 iWinNTHdr = data[63]<<24 | data[62]<<16 | data[61] << 8 | data[60];  
  
      // Verify this is an NT address  
      if ((data[iWinNTHdr+3] << 24 | data[iWinNTHdr+2] << 16 | data[iWinNTHdr+1] << 8 | data[iWinNTHdr]) != 0x00004550)  
         return CompilationMode::Invalid;  
  
      Int32 iLightningAddr = iWinNTHdr + 24 + 208;  
      Int32 iSum = 0;  
      Int32 iTop = iLightningAddr + 8;  
  
      for (int i = iLightningAddr; i < iTop; ++i)  
         iSum |= data[i];  
  
      if (iSum == 0)  
         return CompilationMode::Native;  
      else  
         return CompilationMode::CLR;  
   }  
   catch(Exception ^e) {  
      throw(e);  
   }  
}  
  
int main() {  
   array<String^>^ args = Environment::GetCommandLineArgs();  
  
   if (args->Length < 2) {  
      Console::WriteLine("USAGE : detect_clr <assembly_name>\n");  
      return -1;  
   }  
  
   Console::WriteLine("{0} is compiled {1}", args[1], IsManaged(args[1]));  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)