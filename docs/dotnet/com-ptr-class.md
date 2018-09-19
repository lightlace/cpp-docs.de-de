---
title: 'com:: PTR-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- com::ptr
- msclr::com::ptr
- msclr.com.ptr
- com.ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3cd5b4115d50f9e2db9b1e3dc8a03818e2c8252f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066726"
---
# <a name="comptr-class"></a>com::ptr-Klasse
Ein Wrapper für ein COM-Objekt, das als Mitglied einer CLR-Klasse verwendet werden kann.  Der Wrapper automatisiert auch die Verwaltung der Lebensdauer der COM-Objekts, das alle im Besitz des Benutzers Verweise auf das Objekt freigeben, wenn der Destruktor aufgerufen wird. Analog zu [CComPtr-Klasse](../atl/reference/ccomptr-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### <a name="parameters"></a>Parameter  
*_interface_type*<br/>
COM-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Ein `com::ptr` kann auch als eine lokale Funktion-Variable verwendet werden, um die verschiedenen COM-Aufgaben zu vereinfachen und Automatisieren der Verwaltung der Lebensdauer.  
  
 Ein `com::ptr` kann nicht direkt als Funktionsparameter verwendet werden; verwenden Sie eine [Verweisoperator nachverfolgung](../windows/tracking-reference-operator-cpp-component-extensions.md) oder [Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) stattdessen.  
  
 Ein `com::ptr` nicht direkt von einer Funktion zurückgegeben werden; verwenden Sie stattdessen ein Handle.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die öffentlichen Methoden die Ergebnisse für die Klasse in Aufrufen an die enthaltene Aufrufen `IXMLDOMDocument` Objekt.  Das Beispiel erstellt eine Instanz eines XML-Dokuments, füllt es mit einigen einfachen XML- und eine vereinfachte exemplarische der Knoten in der analysierten Dokumentstruktur den XML-Code in der Konsole gedruckt wird.  
  
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
  
```Output  
<word>persnickety</word>  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Unterstützungsbibliothek](../dotnet/cpp-support-library.md)   
 [ptr-Member](../dotnet/ptr-members.md)