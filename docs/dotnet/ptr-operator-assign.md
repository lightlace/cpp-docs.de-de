---
title: PTR::Operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.operator=
- msclr.com.ptr.operator=
- msclr::com::ptr::operator=
- ptr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator=
ms.assetid: 58619910-46c0-4db8-b183-c811b23b2df1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e58d177a8d12970ec5c4b9d1b8b86405f153bdc3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ptroperator"></a>ptr::operator=
Fügt ein COM-Objekt an eine `com::ptr`.  
  
## <a name="syntax"></a>Syntax  
  
```  
ptr<_interface_type> % operator=(  
   _interface_type * _right  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `_right`  
 Die COM-Schnittstellenzeiger, der angefügt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Nachverfolgungsverweis auf die `com::ptr`.  
  
## <a name="exceptions"></a>Ausnahmen  
 Wenn die `com::ptr` besitzt bereits einen Verweis auf ein COM-Objekt `operator=` löst <xref:System.InvalidOperationException>.  
  
## <a name="remarks"></a>Hinweise  
 Zuweisen von einem COM-Objekt ein `com::ptr` verweist auf das COM-Objekt jedoch nicht den Aufrufer Verweis darauf freigibt.  
  
 Dieser Operator hat dieselbe Wirkung wie das `Attach`.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die `ReplaceDocument` erste Memberfunktion ruft `Release` auf einem beliebigen zuvor Besitzer, Objekt zugewiesen und dann verwendet `operator=` ein neues Dokumentobjekt angefügt.  
  
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
 [PTR-Member](../dotnet/ptr-members.md)   
 [PTR::Attach](../dotnet/ptr-attach.md)   
 [PTR::Detach](../dotnet/ptr-detach.md)   
 [ptr::Release](../dotnet/ptr-release.md)