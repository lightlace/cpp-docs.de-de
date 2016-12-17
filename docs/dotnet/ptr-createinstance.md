---
title: "ptr::CreateInstance"
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
  - "ptr.CreateInstance"
  - "msclr::com::ptr::CreateInstance"
  - "msclr.com.ptr.CreateInstance"
  - "ptr::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::CreateInstance"
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Instanz eines COM\-Objekts in `com::ptr`.  
  
## Syntax  
  
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
  
#### Parameter  
 `progid`  
 Eine `ProgID`\-Zeichenfolge.  
  
 `pouter`  
 Zeiger zur gesamten IUnknown\-Schnittstelle des Objekts \(steuernde IUnknown\).  Wenn `pouter` nicht angegeben wird, wird `NULL` verwendet.  
  
 `cls_context`  
 Kontext, in den der Code, der Verwaltung, das neu erstellte Objekt ausgeführt wird.  Die Werte werden von der `CLSCTX`\-Enumeration verwendet.  Wenn `cls_context` nicht angegeben wird, wird der Wert CLSCTX\_ALL verwendet.  
  
 `rclsid`  
 `CLSID` zugeordneten Daten und dem Code, die verwendet werden, um das Objekt zu erstellen.  
  
## Ausnahmen  
 Wenn `com::ptr` bereits einen Verweis auf ein COM\-Objekt besitzt, wird `CreateInstance`<xref:System.InvalidOperationException> ausgelöst.  
  
 Diese Funktion ruft `CoCreateInstance` und <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR*> verwendet, einen Fehler `HRESULT` in eine entsprechende Ausnahme zu konvertieren.  
  
## Hinweise  
 `CreateInstance`, mit `CoCreateInstance` eine neue Instanz des angegebenen Objekts zu erstellen, der entweder über eine Programm\-ID oder einem CLSID.  `com::ptr` verweist das neu erstellte Objekt wird automatisch alle zugehörigen Verweise nach Zerstörung freigeben.  
  
## Beispiel  
 Dieses Beispiel implementiert eine CLR\-Klasse, die `com::ptr` verwendet, um sein `IXMLDOMDocument`\-Objekt des privaten Members zu umschließen.  Die Klassenkonstruktoren werden zwei unterschiedliche Formulare von `CreateInstance`, um das Dokumentobjekt entweder einer Programm\-ID oder einem CLSID plus ein CLSCTX zu erstellen.  
  
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
  
## Anforderungen  
 **Headerdatei** \<msclr\\com\\ptr.h\>  
  
 **Namespace** msclr::com  
  
## Siehe auch  
 [ptr\-Member](../dotnet/ptr-members.md)