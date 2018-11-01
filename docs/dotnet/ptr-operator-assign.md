---
title: ptr::operator=
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr.operator=
- msclr.com.ptr.operator=
- msclr::com::ptr::operator=
- ptr::operator=
helpviewer_keywords:
- operator=
ms.assetid: 58619910-46c0-4db8-b183-c811b23b2df1
ms.openlocfilehash: c127d2d599be48d4dc406f6e326211591cc8bc66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527919"
---
# <a name="ptroperator"></a>ptr::operator=

Fügt einem COM-Objekt ein `com::ptr`.

## <a name="syntax"></a>Syntax

```
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

#### <a name="parameters"></a>Parameter

*_Right*<br/>
Die COM-Schnittstellenzeiger, der angefügt werden soll.

## <a name="return-value"></a>Rückgabewert

Ein Nachverfolgungsverweis auf die `com::ptr`.

## <a name="exceptions"></a>Ausnahmen

Wenn die `com::ptr` bereits einen Verweis auf ein COM-Objekt im Besitz `operator=` löst <xref:System.InvalidOperationException>.

## <a name="remarks"></a>Hinweise

Zuweisen von einem COM-Objekt ein `com::ptr` verweist auf das COM-Objekt, jedoch nicht des Aufrufers Verweis freigibt.

Dieser Operator hat dieselbe Wirkung wie das `Attach`.

## <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die `ReplaceDocument` erste Memberfunktion `Release` auf eine zuvor im Besitz-Objekt und dann verwendet, `operator=` , fügen Sie ein neues Dokumentobjekt.

```
// comptr_op_assign.cpp
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

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc = pDoc;
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by the ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Siehe auch

[ptr-Member](../dotnet/ptr-members.md)<br/>
[ptr::Attach](../dotnet/ptr-attach.md)<br/>
[ptr::Detach](../dotnet/ptr-detach.md)<br/>
[ptr::Release](../dotnet/ptr-release.md)