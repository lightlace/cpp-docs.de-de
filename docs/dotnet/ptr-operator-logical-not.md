---
title: ptr::operator!
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr::operator!
- msclr::com::ptr::operator!
- ptr.operator!
- msclr.com.ptr.operator!
helpviewer_keywords:
- ptr::operator!
ms.assetid: 7f4101dc-2045-42e7-abb1-6a30e17147f2
ms.openlocfilehash: 8527afe20bf0b0896f2bd433b3dd3e4e8057357b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580894"
---
# <a name="ptroperator"></a>ptr::operator!

Operator, um zu bestimmen, ob das im Besitz des Benutzers COM-Objekt ungültig ist.

## <a name="syntax"></a>Syntax

```
bool operator!();
```

## <a name="return-value"></a>Rückgabewert

**"true"** ist das im Besitz des Benutzers COM-Objekt ungültig; **"false"** andernfalls.

## <a name="remarks"></a>Hinweise

Das COM-Objekt im Besitz des Benutzers ist gültig, wenn er nicht ist **"nullptr"**.

## <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die `CreateInstance` Memberfunktion verwendet `operator!` zu bestimmen, ob ein Document-Objekt ist bereits im Besitz und eine neue Instanz nur, erstellt Wenn das Objekt ungültig ist.

```cpp
// comptr_op_not.cpp
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
         if (m_ptrDoc) {
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

```Output
DOM Document created.
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\com\ptr.h >

**Namespace** msclr::com

## <a name="see-also"></a>Siehe auch

[ptr-Member](../dotnet/ptr-members.md)<br/>
[ptr::operator bool](../dotnet/ptr-operator-bool.md)