---
title: "ptr::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr.QueryInterface"
  - "ptr::QueryInterface"
  - "msclr::com::ptr::QueryInterface"
  - "msclr.com.ptr.QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface-Methode"
ms.assetid: c2619517-3fde-493b-b12d-da8f62d5d803
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ptr::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fragt das Besitze COM\-Objekt für eine Schnittstelle ab und fügt das Ergebnis in einen anderen `com::ptr`.  
  
## Syntax  
  
```  
template<class _other_type>  
void QueryInterface(  
   ptr<_other_type> % other  
);  
```  
  
#### Parameter  
 `other`  
 `com::ptr`, das die Schnittstelle abgerufen.  
  
## Ausnahmen  
 Intern wird `QueryInterface` für den besitzenden COM\-Objekt aufgerufen und jeder Fehler `HRESULT` wird einer Ausnahme von <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR*> konvertiert.  
  
## Hinweise  
 Verwenden Sie diese Methode, um einen COM\-Wrapper für eine andere Schnittstelle des COM\-Objekts zu erstellen, das vom aktuellen Wrapper verwendet wird.  Diese Methode ruft `QueryInterface` durch das Besitze COM\-Objekt, einen Zeiger auf eine bestimmte Schnittstelle des COM\-Objekts und der wird der zurückgegebene Schnittstellenzeiger zu übergebenen `com::ptr`\- Informationen.  
  
## Beispiel  
 Dieses Beispiel implementiert eine CLR\-Klasse, die `com::ptr` verwendet, um sein `IXMLDOMDocument`\-Objekt des privaten Members zu umschließen.  Die `WriteTopLevelNode`\-Memberfunktion wird `QueryInterface` verwendet, um lokalen `com::ptr` mit `IXMLDOMNode` auszufüllen und dann `com::ptr` \(mithilfe Nachverfolgungsverweis\) in einer privaten Memberfunktion, die die Namens\- und Texteigenschaften des Knotens an die Konsole ausgibt.  
  
```  
// comptr_queryinterface.cpp  
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
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   void LoadXml(String^ xml) {  
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);  
      BSTR bstr = NULL;  
  
      try {  
         // load some XML into our document  
         bstr = ::SysAllocString(pinnedXml);  
         if (NULL == bstr) {  
            throw gcnew OutOfMemoryException;  
         }  
         VARIANT_BOOL bIsSuccessful = false;  
         // use operator -> to call IXMODOMDocument member function  
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   // write the top level node to the console  
   void WriteTopLevelNode() {  
      com::ptr<IXMLDOMNode> ptrNode;  
  
      // query for the top level node interface  
      m_ptrDoc.QueryInterface(ptrNode);  
      WriteNode(ptrNode);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(com::ptr<IXMLDOMNode> % node) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(node->get_text(&bstr));  
         Console::Write(gcnew String(bstr));  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Console::WriteLine("</{0}>", strName);  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // stream some xml into the document  
      doc.LoadXml("<word>persnickety</word>");  
  
      // write the document to the console  
      doc.WriteTopLevelNode();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **\<\#documentpersnickety\/\#document\>\<\>**   
## Anforderungen  
 **Headerdatei** \<msclr\\com\\ptr.h\>  
  
 **Namespace** msclr::com  
  
## Siehe auch  
 [ptr\-Member](../dotnet/ptr-members.md)   
 [ptr::GetInterface](../dotnet/ptr-getinterface.md)