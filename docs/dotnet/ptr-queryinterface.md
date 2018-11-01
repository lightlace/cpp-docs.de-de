---
title: ptr::QueryInterface
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr.QueryInterface
- ptr::QueryInterface
- msclr::com::ptr::QueryInterface
- msclr.com.ptr.QueryInterface
helpviewer_keywords:
- QueryInterface method
ms.assetid: c2619517-3fde-493b-b12d-da8f62d5d803
ms.openlocfilehash: f596a26213ad75bc835b01e69fe57cece580f8ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677447"
---
# <a name="ptrqueryinterface"></a>ptr::QueryInterface

Fragt das im Besitz des Benutzers COM-Objekt für eine Schnittstelle ab und fügt das Ergebnis in eine andere `com::ptr`.

## <a name="syntax"></a>Syntax

```
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

#### <a name="parameters"></a>Parameter

*other*<br/>
Die `com::ptr` erhalten, die die Schnittstelle.

## <a name="exceptions"></a>Ausnahmen

Intern `QueryInterface` aufgerufen wird, auf das im Besitz des Benutzers COM-Objekt und alle Fehler `HRESULT` konvertiert wird, um eine Ausnahme von <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein COM-Wrapper für eine andere Schnittstelle des COM-Objekts, das im Besitz von aktuellen Wrapper erstellen. Diese Methode ruft `QueryInterface` über das im Besitz des Benutzers COM-Objekt zum Anfordern der eines Zeigers auf eine bestimmte Schnittstelle die COM-Objekt, und fügt den zurückgegebenen Schnittstellenzeiger in den übergebenen `com::ptr`.

## <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `WriteTopLevelNode` Memberfunktion verwendet `QueryInterface` , geben Sie eine lokale `com::ptr` mit einer `IXMLDOMNode` und übergibt dann die `com::ptr` (durch ein Nachverfolgungsverweis) auf einen privaten Member-Funktion, die den Namen und Text-Eigenschaften des Knotens in die Konsole schreibt.

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

```Output
<#document>persnickety</#document>
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Siehe auch

[ptr-Member](../dotnet/ptr-members.md)<br/>
[ptr::GetInterface](../dotnet/ptr-getinterface.md)