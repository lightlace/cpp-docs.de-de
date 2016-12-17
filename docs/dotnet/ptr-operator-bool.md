---
title: "ptr::operator bool"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ptr::operator bool"
  - "ptr.operator bool"
  - "operator bool"
  - "msclr::com::ptr::operator bool"
  - "msclr.com.ptr.operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::operator bool"
ms.assetid: 31123377-6ecd-4cef-9b75-3db3996fbcd1
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Operator für die Anwendung von `com::ptr` in einem Bedingungsausdruck.  
  
## Syntax  
  
```  
operator bool();  
```  
  
## Rückgabewert  
 `true`, wenn das Besitze COM\-Objekt gültig ist; andernfalls `false`.  
  
## Hinweise  
 Das Besitze COM\-Objekt ist gültig, wenn er nicht `nullptr` ist.  
  
 Dieser Operator konvertiert tatsächlich an eine `_detail_class::_safe_bool`, die sicherer als `bool` ist, da es nicht zu einem ganzzahligen Typ konvertiert werden kann.  
  
## Beispiel  
 Dieses Beispiel implementiert eine CLR\-Klasse, die `com::ptr` verwendet, um sein `IXMLDOMDocument`\-Objekt des privaten Members zu umschließen.  Die `CreateInstance`\-Memberfunktion verwendet `operator bool`, nachdem das Dokumentobjekt neue erstellt hat, um zu bestimmen, ob sie gültig und schreibt in Konsole, wenn sie ist.  
  
```  
// comptr_op_bool.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   void CreateInstance(String^ progid) {  
      if (!m_ptrDoc) {  
         m_ptrDoc.CreateInstance(progid);     
         if (m_ptrDoc) { // uses operator bool  
            Console::WriteLine("DOM Document created.");  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      XmlDocument doc;  
      // create the instance from a progid string  
      doc.CreateInstance("Msxml2.DOMDocument.3.0");  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **DOM\-Dokument erstellt.**   
## Anforderungen  
 **Headerdatei** \<msclr\\com\\ptr.h\>  
  
 **Namespace** msclr::com  
  
## Siehe auch  
 [ptr\-Member](../dotnet/ptr-members.md)   
 [ptr::operator\!](../dotnet/ptr-operator-logical-not.md)