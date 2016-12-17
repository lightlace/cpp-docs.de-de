---
title: "com::ptr-Klasse"
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
  - "com::ptr"
  - "msclr::com::ptr"
  - "msclr.com.ptr"
  - "com.ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr-Klasse"
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# com::ptr-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für ein COM\-Objekt, die als Member einer CLR\-Klasse verwendet werden kann.  Der Wrapper automatisiert zudem die Lebensdauerverwaltung des COM\-Objekts und gibt alle zugehörigen Verweise auf das Objekt frei, wenn ihr Destruktor aufgerufen wird.  Analog [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## Syntax  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### Parameter  
 `_interface_type`  
 COM\-Schnittstelle.  
  
## Hinweise  
 `com::ptr` kann als lokale Funktionsvariable auch verwendet werden, um verschiedene COM\-Aufgaben vereinfachen und Lebensdauerverwaltung zu automatisieren.  
  
 `com::ptr` kann nicht direkt als Funktionsparameter verwendet werden; verwenden Sie [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) oder [Handle für Objekt \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
 `com::ptr` kann nicht von einer Funktion zurückgegeben werden direkt; verwenden Sie ein Handle stattdessen.  
  
## Beispiel  
 Dieses Beispiel implementiert eine CLR\-Klasse, die `com::ptr` verwendet, um sein `IXMLDOMDocument`\-Objekt des privaten Members zu umschließen.  Die öffentlichen Methoden der Klassenergebnisse in Aufrufen zum enthaltenden `IXMLDOMDocument` aufrufen, Objekts.  Das Beispiel erstellt eine Instanz eines XML\-Dokuments, füllt sie mit einfachem XML aus und führt einen vereinfachten Bearbeitung der Knoten der analysierten Dokumentstruktur, um XML auf der Konsole auszugeben.  
  
```  
// comptr.cpp  
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
         // load some XML into the document  
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
  
   // simplified function to write just the first xml node to the console  
   void WriteXml() {  
      IXMLDOMNode* pNode = NULL;  
  
      try {  
         // the first child of the document is the first real xml node  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            WriteNode(pNode);  
         }  
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(IXMLDOMNode* pNode) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));  
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
      doc.WriteXml();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **\<wordpersnickety\>\<\/Wort\>**   
## Anforderungen  
 **Headerdatei** \<msclr\\com\\ptr.h\>  
  
 **Namespace** msclr::com  
  
## Siehe auch  
 [C\+\+\-Unterstützungsbibliothek](../dotnet/cpp-support-library.md)   
 [ptr\-Member](../dotnet/ptr-members.md)