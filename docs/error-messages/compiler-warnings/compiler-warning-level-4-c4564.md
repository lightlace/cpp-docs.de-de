---
title: "Compilerwarnung (Stufe 4) C4564"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4564"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4564"
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4564
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Methode 'Methode' von Klasse 'Klasse' definiert den nicht unterstützten Standardparameter 'Parameter'  
  
 Der Compiler hat eine Methode mit einem oder mehreren Parametern gefunden, die Standardwerte aufweisen.  Die Standardwerte für die Parameter werden beim Aufrufen der Methode ignoriert. Legen Sie Werte für diese Parameter explizit fest.  Wenn Sie Werte für diese Parameter nicht explizit festlegen, generiert der C\+\+\-Compiler einen Fehler.  
  
 Angenommen, Sie verfügen über die folgende, mit Visual Basic erstellte DLL, die Standardparameter für Methodenargumente zulässt:  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 und über folgenden C\+\+\-Beispielcode, der die mit Visual Basic erstellte DLL verwendet  
  
```  
// C4564.cpp  
// compile with: /clr /W4 /WX  
#using <C4564.dll>  
  
int main() {  
   TestClass ^ myx = gcnew TestClass();   // C4564  
   myx->MyMethod(9);  
   // try the following line instead, to avoid an error  
   // myx->MyMethod(9, 1);  
}  
```