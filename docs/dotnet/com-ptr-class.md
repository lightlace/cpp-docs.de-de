---
title: com::ptr-Klasse
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::com::ptr::ptr
- msclr::com::ptr::Attach
- msclr::com::ptr::CreateInstance
- msclr::com::ptr::Detach
- msclr::com::ptr::GetInterface
- msclr::com::ptr::QueryInterface
- msclr::com::ptr::Release
- msclr::com::ptr::operator=
- msclr::com::ptr::operator->
- msclr::com::ptr::operator!
helpviewer_keywords:
- msclr::ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
ms.openlocfilehash: 8909f91e31279f1fc1395610aea4708b79731113
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805967"
---
# <a name="comptr-class"></a>com::ptr-Klasse

Ein Wrapper für ein COM-Objekt, das als Mitglied einer CLR-Klasse verwendet werden kann.  Der Wrapper automatisiert auch die Verwaltung der Lebensdauer der COM-Objekts, das alle im Besitz des Benutzers Verweise auf das Objekt freigeben, wenn der Destruktor aufgerufen wird. Analog zu [CComPtr-Klasse](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Syntax

```
template<class _interface_type>
ref class ptr;
```

### <a name="parameters"></a>Parameter

*_interface_type*<br/>
COM-Schnittstelle.

## <a name="remarks"></a>Hinweise

Ein `com::ptr` kann auch als eine lokale Funktion-Variable verwendet werden, um die verschiedenen COM-Aufgaben zu vereinfachen und Automatisieren der Verwaltung der Lebensdauer.

Ein `com::ptr` kann nicht direkt als Funktionsparameter verwendet werden; verwenden Sie eine [nachverfolgung verweisoperator](../windows/tracking-reference-operator-cpp-component-extensions.md) oder [Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) stattdessen.

Ein `com::ptr` nicht direkt von einer Funktion zurückgegeben werden; verwenden Sie stattdessen ein Handle.

## <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die öffentlichen Methoden die Ergebnisse für die Klasse in Aufrufen an die enthaltene Aufrufen `IXMLDOMDocument` Objekt.  Das Beispiel erstellt eine Instanz eines XML-Dokuments, füllt es mit einigen einfachen XML- und eine vereinfachte exemplarische der Knoten in der analysierten Dokumentstruktur den XML-Code in der Konsole gedruckt wird.

```cpp
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

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|name|Beschreibung| 
|---------|-----------| 
|[ptr::ptr](#ptr)|Erstellt eine `com::ptr` ein COM-Objekt umschlossen.| 
|[ptr::~ptr](#tilde-ptr)|Destructs eine `com::ptr`.| 

### <a name="public-methods"></a>Öffentliche Methoden

|name|Beschreibung|
|---------|-----------| 
|[ptr::Attach](#attach)|Fügt einem COM-Objekt ein `com::ptr`.| 
|[ptr::CreateInstance](#createInstance)|Erstellt eine Instanz eines COM-Objekts innerhalb einer `com::ptr`.| 
|[ptr::Detach](#detach)|Gibt den Besitz der das COM-Objekt, das einen Zeiger auf das Objekt zurückgibt.| 
|[ptr::GetInterface](#getInterface)|Erstellt eine Instanz eines COM-Objekts innerhalb einer `com::ptr`.| 
|[ptr::QueryInterface](#queryInterface)|Fragt das im Besitz des Benutzers COM-Objekt für eine Schnittstelle ab und fügt das Ergebnis in eine andere `com::ptr`.| 
|[ptr::Release](#release)|Gibt alle im Besitz des Benutzers Verweise auf COM-Objekts frei.|

### <a name="public-operators"></a>Öffentliche Operatoren

|name|Beschreibung|
|---------|-----------| 
|[ptr::operator-&gt;](#operator-arrow)|Memberzugriffsoperator, zum Aufrufen von Methoden für das COM-Objekt im Besitz des Benutzers verwendet.| 
|[ptr::operator=](#operator-assign)|Fügt einem COM-Objekt ein `com::ptr`.| 
|[ptr::operator&nbsp;bool](#operator-bool)|Operator für die Verwendung von `com::ptr` in einem bedingten Ausdruck.| 
|[ptr::operator!](#operator-logical-not)|Operator, um zu bestimmen, ob das im Besitz des Benutzers COM-Objekt ungültig ist.| 

## <a name="requirements"></a>Anforderungen

**Header file** \<msclr\com\ptr.h>

**Namespace** msclr::com

 

## <a name="ptr"></a>ptr::ptr

Gibt einen Zeiger auf die im Besitz des Benutzers COM-Objekt.

```cpp
ptr();
ptr(
   _interface_type * p
);
```

### <a name="parameters"></a>Parameter

*P*<br/>
Ein COM-Schnittstellenzeiger.

### <a name="remarks"></a>Hinweise

Der Konstruktor ohne Argument weist `nullptr` an das zugrunde liegende Objekthandle. Zukünftige Aufrufe an die `com::ptr` wird das interne Objekt überprüfen und ohne Meldung fehl, bis ein Objekt erstellt oder angefügt wird.

Der einem Argument-Konstruktor fügt einen Verweis auf das COM-Objekt, jedoch nicht des Aufrufers-Verweis, nicht freigeben, damit der Aufrufer aufrufen muss `Release` für die COM-Objekt, um wirklich Kontrolle zu gewähren. Wenn die `com::ptr`der Destruktor aufgerufen wird es automatisch freigibt, Verweise auf die COM-Objekt.

Übergeben von `NULL` an diesen Konstruktor entspricht dem Aufrufen der Version für die keine Argumente.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Es veranschaulicht die Verwendung beider Versionen des Konstruktors.

```cpp
// comptr_ptr.cpp
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

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
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

## <a name="tilde-ptr"></a>ptr::~ptr

Destructs eine `com::ptr`.

```cpp
~ptr();
```

### <a name="remarks"></a>Hinweise

Der Zerstörung der `com::ptr` gibt alle Verweise, die es, auf die COM-Objekt besitzt frei. Vorausgesetzt, es keine weiteren Verweise frei, die auf die COM-Objekt sind, das COM-Objekt gelöscht werden, und dessen Speicher freigegeben.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  In der `main` -Funktion, die beiden `XmlDocument` Destruktor des Objekts werden aufgerufen, wenn sie den Geltungsbereich verlässt die `try` blockieren, was in der zugrunde liegenden `com::ptr` Destruktor aufgerufen wird, Freigabe alle im Besitz des Benutzers Verweise auf COM -Objekt.

```cpp
// comptr_dtor.cpp
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

   // construct the internal com::ptr with a COM object
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create an XML DOM document object
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));
      // construct the ref class with the COM object
      XmlDocument doc1(pDoc);

      // or create the class from a progid string
      XmlDocument doc2("Msxml2.DOMDocument.3.0");
   }
   // doc1 and doc2 destructors are called when they go out of scope
   // and the internal com::ptr releases its reference to the COM object
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

## <a name="attach"></a>ptr::Attach

Fügt einem COM-Objekt ein `com::ptr`.

```cpp
void Attach(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parameter

*_right*<br/>
Die COM-Schnittstellenzeiger, der angefügt werden soll.

### <a name="exceptions"></a>Ausnahmen

Wenn die `com::ptr` bereits einen Verweis auf ein COM-Objekt im Besitz `Attach` löst <xref:System.InvalidOperationException>.

### <a name="remarks"></a>Hinweise

Ein Aufruf von `Attach` verweist auf das COM-Objekt ohne Verweis des Aufrufers freizugeben.

Übergeben von `NULL` zu `Attach` führt keine Aktion ausgeführt wird.

### <a name="example"></a>Beispiel

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

## <a name="createInstance"></a>ptr::CreateInstance

Erstellt eine Instanz eines COM-Objekts innerhalb einer `com::ptr`.

```cpp
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

### <a name="parameters"></a>Parameter

*progid*<br/>
Eine `ProgID`-Zeichenfolge.

*pouter*<br/>
Zeiger auf IUnknown-Schnittstelle des aggregierten Objekts (das "controlling IUnknown"). Wenn `pouter` nicht angegeben ist, `NULL` verwendet wird.

*cls_context*<br/>
Der Kontext, in dem der Code, der das neu erstellte Objekt verwaltet ausgeführt wird. Die Werte stammen aus der `CLSCTX` Enumeration. Wenn `cls_context` nicht angegeben ist, den Wert CLSCTX_ALL verwendet wird.

*rclsid*<br/>
`CLSID` zugeordnet mit den Daten und Code, der zum Erstellen des Objekts verwendet wird.

### <a name="exceptions"></a>Ausnahmen

Wenn die `com::ptr` bereits einen Verweis auf ein COM-Objekt im Besitz `CreateInstance` löst <xref:System.InvalidOperationException>.

Diese Funktion ruft `CoCreateInstance` und verwendet <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> Fehler konvertieren `HRESULT` auf eine entsprechende Ausnahme.

### <a name="remarks"></a>Hinweise

`CreateInstance` verwendet `CoCreateInstance` zum Erstellen einer neuen Instanz des angegebenen Objekts, identifiziert werden, entweder über eine ProgID oder CLSID. Die `com::ptr` verweist auf das neu erstellte Objekt und alle im Besitz des Benutzers Verweise nach der Destruktion automatisch freigibt.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die Klasse, Konstruktoren verwenden zwei verschiedene Arten von `CreateInstance` auf das Document-Objekt entweder aus eine ProgID oder CLSID plus eine CLSCTX erstellen.

```cpp
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

## <a name="detach"></a>ptr::Detach

Gibt den Besitz der das COM-Objekt, das einen Zeiger auf das Objekt zurückgibt.

```cpp
_interface_type * Detach();
```

### <a name="return-value"></a>Rückgabewert

Der Zeiger auf das COM-Objekt.

Wenn kein Objekt einen Besitzer hat, wird NULL zurückgegeben.

### <a name="exceptions"></a>Ausnahmen

Intern `QueryInterface` aufgerufen wird, auf das im Besitz des Benutzers COM-Objekt und alle Fehler `HRESULT` konvertiert wird, um eine Ausnahme von <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Hinweise

`Detach` zuerst Fügt einen Verweis auf das COM-Objekt im Namen des Aufrufers, und klicken Sie dann frei alle Verweise, die im Besitz der `com::ptr`.  Der Aufrufer muss das zurückgegebene Objekt, um es zu zerstören letztlich freigeben.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die `DetachDocument` Memberfunktion ruft `Detach` Geben Sie den Besitz des COM-Objekts, und geben Sie einen Zeiger an den Aufrufer zurück.

```cpp
// comptr_detach.cpp
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

   // detach the COM object and return it
   // this releases the internal reference to the object
   IXMLDOMDocument* DetachDocument() {
      return m_ptrDoc.Detach();
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.DetachDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release document object as the ref class no longer owns it
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

## <a name="getInterface"></a>ptr::GetInterface

Gibt einen Zeiger auf die im Besitz des Benutzers COM-Objekt.

```cpp
_interface_type * GetInterface();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das im Besitz des Benutzers COM-Objekt.

### <a name="exceptions"></a>Ausnahmen

Intern `QueryInterface` aufgerufen wird, auf das im Besitz des Benutzers COM-Objekt und alle Fehler `HRESULT` konvertiert wird, um eine Ausnahme von <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Hinweise

Die `com::ptr` Fügt einen Verweis auf das COM-Objekt, auf den Namen des Aufrufers erstellt und bleibt auch seinen eigenen Verweis auf das COM-Objekt. Der Aufrufer muss den Verweis auf das zurückgegebene Objekt letztlich freigeben, oder es wird nicht zerstört werden.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `GetDocument` Memberfunktion verwendet `GetInterface` um einen Zeiger auf die COM-Objekt zurückzugeben.

```cpp
// comptr_getinterface.cpp
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

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
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
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
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

```Output
<word>persnickety</word>
```

## <a name="queryInterface"></a>ptr::QueryInterface

Fragt das im Besitz des Benutzers COM-Objekt für eine Schnittstelle ab und fügt das Ergebnis in eine andere `com::ptr`.

```cpp
template<class _other_type>
void QueryInterface(
   ptr<_other_type> % other
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Die `com::ptr` erhalten, die die Schnittstelle.

### <a name="exceptions"></a>Ausnahmen

Intern `QueryInterface` aufgerufen wird, auf das im Besitz des Benutzers COM-Objekt und alle Fehler `HRESULT` konvertiert wird, um eine Ausnahme von <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein COM-Wrapper für eine andere Schnittstelle des COM-Objekts, das im Besitz von aktuellen Wrapper erstellen. Diese Methode ruft `QueryInterface` über das im Besitz des Benutzers COM-Objekt zum Anfordern der eines Zeigers auf eine bestimmte Schnittstelle die COM-Objekt, und fügt den zurückgegebenen Schnittstellenzeiger in den übergebenen `com::ptr`.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `WriteTopLevelNode` Memberfunktion verwendet `QueryInterface` , geben Sie eine lokale `com::ptr` mit einer `IXMLDOMNode` und übergibt dann die `com::ptr` (durch ein Nachverfolgungsverweis) auf einen privaten Member-Funktion, die den Namen und Text-Eigenschaften des Knotens in die Konsole schreibt.

```cpp
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

## <a name="release"></a>ptr::Release

Gibt alle im Besitz des Benutzers Verweise auf COM-Objekts frei.

```cpp
void Release();
```

### <a name="remarks"></a>Hinweise

Alle im Besitz des Benutzers Verweise auf COM-Objekts frei und legt das interne Handle auf das COM-Objekt, das Aufrufen dieser Funktion `nullptr`.  Wenn keine weiteren Verweise auf das COM-Objekt vorhanden ist, wird es zerstört werden.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die `ReplaceDocument` Memberfunktion verwendet `Release` , alle vorherigen Document-Objekt freizugeben, bevor Sie das neue Dokument angehängt.

```cpp
// comptr_release.cpp
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

## <a name="operator-arrow"></a>ptr::operator-&gt;

Memberzugriffsoperator, zum Aufrufen von Methoden für das COM-Objekt im Besitz des Benutzers verwendet.

```cpp
_detail::smart_com_ptr<_interface_type> operator->();
```

### <a name="return-value"></a>Rückgabewert

Ein `smart_com_ptr` zum COM-Objekt.

### <a name="exceptions"></a>Ausnahmen

Intern `QueryInterface` aufgerufen wird, auf das im Besitz des Benutzers COM-Objekt und alle Fehler `HRESULT` konvertiert wird, um eine Ausnahme von <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.

### <a name="remarks"></a>Hinweise

Dieser Operator können Sie zum Aufrufen von Methoden des COM-Objekts im Besitz des Benutzers. Gibt ein temporäres `smart_com_ptr` , die behandelt automatisch eine eigene `AddRef` und `Release`.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `WriteDocument` Funktion verwendet `operator->` zum Aufrufen der `get_firstChild` Mitglied das Document-Objekt.

```cpp
// comptr_op_member.cpp
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

   // add a reference to and return the COM object
   // but keep an internal reference to the object
   IXMLDOMDocument* GetDocument() {
      return m_ptrDoc.GetInterface();
   }

   // simplified function that only writes the first node
   void WriteDocument() {
      IXMLDOMNode* pNode = NULL;
      BSTR bstr = NULL;

      try {
         // use operator -> to call XML Doc member
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));
         if (NULL != pNode) {
            // write out the xml
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
      }
      finally {
         if (NULL != pNode) {
            pNode->Release();
         }
         ::SysFreeString(bstr);
      }
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that loads XML into a raw XML DOM Document object
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {
   HRESULT hr = S_OK;
   VARIANT_BOOL bSuccess;
   hr = pDoc->loadXML(bstrXml, &bSuccess);
   if (S_OK == hr && !bSuccess) {
      hr = E_FAIL;
   }
   return hr;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;
   BSTR bstrXml = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      bstrXml = ::SysAllocString(L"<word>persnickety</word>");
      if (NULL == bstrXml) {
         throw gcnew OutOfMemoryException("bstrXml");
      }
      // detach the document object from the ref class
      pDoc = doc.GetDocument();
      // use unmanaged function and raw object to load xml
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));
      // release reference to document object (but ref class still references it)
      pDoc->Release();
      pDoc = NULL;

      // call another function on the ref class
      doc.WriteDocument();
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

```Output
<word>persnickety</word>
```

## <a name="operator-assign"></a>ptr::operator=

Fügt einem COM-Objekt ein `com::ptr`.

```cpp
ptr<_interface_type> % operator=(
   _interface_type * _right
);
```

### <a name="parameters"></a>Parameter

*_right*<br/>
Die COM-Schnittstellenzeiger, der angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Nachverfolgungsverweis auf die `com::ptr`.

### <a name="exceptions"></a>Ausnahmen

Wenn die `com::ptr` bereits einen Verweis auf ein COM-Objekt im Besitz `operator=` löst <xref:System.InvalidOperationException>.

### <a name="remarks"></a>Hinweise

Zuweisen von einem COM-Objekt ein `com::ptr` verweist auf das COM-Objekt ohne Verweis des Aufrufers freizugeben.

Dieser Operator hat dieselbe Wirkung wie das `Attach`.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt.  Die `ReplaceDocument` erste Memberfunktion `Release` auf eine zuvor im Besitz-Objekt und dann verwendet, `operator=` , fügen Sie ein neues Dokumentobjekt.

```cpp
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

## <a name="operator-bool"></a> PTR::Operator "bool"

Operator für die Verwendung von `com::ptr` in einem bedingten Ausdruck.

```cpp
operator bool();
```

### <a name="return-value"></a>Rückgabewert

`true` Wenn das COM-Objekt im Besitz des Benutzers gültig ist. `false` andernfalls.

### <a name="remarks"></a>Hinweise

Das COM-Objekt im Besitz des Benutzers ist gültig, wenn er nicht ist `nullptr`.

Dieser Operator konvertiert in `_detail_class::_safe_bool` ist sicherer als `bool` , da es in einen ganzzahligen Typ konvertiert werden kann.

### <a name="example"></a>Beispiel

In diesem Beispiel implementiert eine CLR-Klasse, verwendet eine `com::ptr` , umschließen die privaten Member `IXMLDOMDocument` Objekt. Die `CreateInstance` Memberfunktion verwendet `operator bool` nach dem Erstellen der neuen Document-Objekt, um zu bestimmen, ob es gültig ist und in die Konsole geschrieben werden, wenn es sich handelt.

```cpp
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

## <a name="operator-logical-not"></a>PTR::Operator!

Operator, um zu bestimmen, ob das im Besitz des Benutzers COM-Objekt ungültig ist.

```cpp
bool operator!();
```

### <a name="return-value"></a>Rückgabewert

`true` Wenn das COM-Objekt im Besitz des Benutzers ungültig ist; `false` andernfalls.

### <a name="remarks"></a>Hinweise

Das COM-Objekt im Besitz des Benutzers ist gültig, wenn er nicht ist `nullptr`.

### <a name="example"></a>Beispiel

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
