---
title: Bool PTR::Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr::operator bool
- ptr.operator bool
- operator bool
- msclr::com::ptr::operator bool
- msclr.com.ptr.operator bool
dev_langs:
- C++
helpviewer_keywords:
- ptr::operator bool
ms.assetid: 31123377-6ecd-4cef-9b75-3db3996fbcd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 263810b4fbd369445c2ead55277381bc81b092d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ptroperator-bool"></a>ptr::operator bool
Operator für die Verwendung von `com::ptr` in einem bedingten Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator bool();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn das im Besitz befindlichen COM-Objekt gültig ist. `false` andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Das im Besitz befindlichen COM-Objekt ist gültig, wenn er nicht ist `nullptr`.  
  
 Dieser Operator konvertiert tatsächlich in `_detail_class::_safe_bool` ist sicherer als `bool` , da es zu einem ganzzahligen Typ konvertiert werden kann.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `CreateInstance` Memberfunktion verwendet `operator bool` nach dem Erstellen der neuen Document-Objekt, um zu bestimmen, ob es gültig ist und in die Konsole geschrieben, wenn es sich handelt.  
  
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
  
```Output  
DOM Document created.  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Siehe auch  
 [PTR-Member](../dotnet/ptr-members.md)   
 [ptr::operator!](../dotnet/ptr-operator-logical-not.md)