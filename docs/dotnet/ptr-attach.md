---
title: PTR::Attach | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::com::ptr::Attach
- ptr::Attach
- ptr.Attach
- msclr.com.ptr.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: 81d930de-cb2a-4c30-9bd6-94d65942c47a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 873a36e69c767a6101173f545520e60bfa6ce598
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315339"
---
# <a name="ptrattach"></a>ptr::Attach

Fügt einem COM-Objekt ein `com::ptr`.

## <a name="syntax"></a>Syntax

```
void Attach(
   _interface_type * _right
);
```

#### <a name="parameters"></a>Parameter

*_Right*<br/>
Die COM-Schnittstellenzeiger, der angefügt werden soll.

## <a name="exceptions"></a>Ausnahmen

Wenn die `com::ptr` bereits einen Verweis auf ein COM-Objekt im Besitz `Attach` löst <xref:System.InvalidOperationException>.

## <a name="remarks"></a>Hinweise

Ein Aufruf von `Attach` verweist auf das COM-Objekt, jedoch nicht des Aufrufers Verweis freigibt.

Übergeben von `NULL` zu `Attach` führt keine Aktion ausgeführt wird.

## <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `ReplaceDocument` erste Memberfunktion `Release` auf eine zuvor im Besitz-Objekt und ruft dann `Attach` , fügen Sie ein neues Dokumentobjekt.

```cpp
// comptr_attach.cpp
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
      m_ptrDoc.Attach(pDoc);
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
      // store it in place of the one held by our ref class
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

**Headerdatei** \<Msclr\\com\\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Siehe auch

[ptr-Member](../dotnet/ptr-members.md)<br/>
[ptr::operator=](../dotnet/ptr-operator-assign.md)<br/>
[ptr::Release](../dotnet/ptr-release.md)