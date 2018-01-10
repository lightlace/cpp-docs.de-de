---
title: PTR::CreateInstance | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.CreateInstance
- msclr::com::ptr::CreateInstance
- msclr.com.ptr.CreateInstance
- ptr::CreateInstance
dev_langs: C++
helpviewer_keywords: ptr::CreateInstance
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d764d18f3148dba663e1e6796c44a0add6aa8109
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ptrcreateinstance"></a>ptr::CreateInstance
Erstellt eine Instanz des COM-Objekt innerhalb einer `com::ptr`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   System::String ^ progid  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   const wchar_t * progid  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   REFCLSID rclsid  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `progid`  
 Eine `ProgID`-Zeichenfolge.  
  
 `pouter`  
 Ein Zeiger auf das Aggregatobjekt IUnknown-Schnittstelle (das "controlling IUnknown"). Wenn `pouter` nicht angegeben ist, `NULL` verwendet wird.  
  
 `cls_context`  
 Der Kontext, in dem der Code, der das neu erstellte Objekt verwaltet ausgeführt wird. Die Werte stammen aus den `CLSCTX` Enumeration. Wenn `cls_context` nicht angegeben ist, der Wert CLSCTX_ALL wird verwendet.  
  
 `rclsid`  
 `CLSID`verknüpft sind mit den Daten und den Code, der zum Erstellen des Objekts verwendet wird.  
  
## <a name="exceptions"></a>Ausnahmen  
 Wenn die `com::ptr` besitzt bereits einen Verweis auf ein COM-Objekt `CreateInstance` löst <xref:System.InvalidOperationException>.  
  
 Diese Funktion ruft `CoCreateInstance` und verwendet <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> Fehler konvertieren `HRESULT` in eine entsprechende Ausnahme.  
  
## <a name="remarks"></a>Hinweise  
 `CreateInstance`verwendet `CoCreateInstance` zum Erstellen einer neuen Instanz des angegebenen Objekts, über den eine ProgID oder CLSID identifiziert. Die `com::ptr` verweist auf das neu erstellte Objekt und alle im Besitz befindlichen Verweise auf die Zerstörung automatisch freigibt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` umschließen die privaten Member `IXMLDOMDocument` Objekt. Die Klasse, Konstruktoren verwenden zwei verschiedene Arten von `CreateInstance` das Document-Objekt aus einem ProgID oder CLSID plus eine CLSCTX erstellen.  
  
```  
// comptr_createinstance.cpp  
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
   XmlDocument(REFCLSID clsid, DWORD clsctx) {  
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc1("Msxml2.DOMDocument.3.0");  
  
      // or from a clsid with specific CLSCTX  
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>Siehe auch  
 [ptr-Member](../dotnet/ptr-members.md)