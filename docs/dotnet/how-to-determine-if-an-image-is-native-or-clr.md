---
title: "Gewusst wie: Ermitteln, ob ein Bild systemeigen oder CLR ist"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Erkennen der Verwendung in Kompilierung"
  - "Common Language Runtime, /clr-Compileroption"
  - "Common Language Runtime, Bildprüfung"
  - "Bilder [C++], CLR-Überprüfung"
ms.assetid: 5a854822-6172-4b22-b236-320165412568
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Ermitteln, ob ein Bild systemeigen oder CLR ist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Möglichkeit, zu ermitteln, ob ein Bild für die Common Language Runtime erstellt wurde, stellt die Option **dumpbin** [\/CLRHEADER](../build/reference/clrheader.md) dar.  
  
 Sie können auch programmgesteuert überprüfen, ob ein Bild für Common Language Runtime erstellt wurde.  Weitere Informationen finden Sie unter [Gewusst wie: Erkennen der \/clr\-Kompilierung](../dotnet/how-to-detect-clr-compilation.md).  
  
## Beispiel  
 Das folgende Beispiel ermittelt, ob ein Bild für die Ausführung in der Common Language Runtime erstellt wurde.  
  
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
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)