---
title: Fragen und Antworten zur attributierten Programmierung
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributed programming
- attributes [C++/CLI], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
ms.openlocfilehash: fd4c24e3933738d128dffd41018466c33b419de8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148366"
---
# <a name="attribute-programming-faq"></a>Fragen und Antworten zur attributierten Programmierung

In diesem Thema werden die folgenden häufig gestellten Fragen beantwortet:

- [Was ist ein HRESULT?](#vcconattributeprogrammmingfaqanchor1)

- [Wenn habe ich den Parameternamen für ein Attribut angeben?](#vcconattributeprogrammmingfaqanchor2)

- [Kann ich Kommentare in einem Attributblock verwenden?](#vcconattributeprogrammmingfaqanchor3)

- [Wie interagieren Attribute mit Vererbung?](#vcconattributeprogrammmingfaqanchor4)

- [Wie kann ich die Attribute in einem nicht attributierte ATL-Projekt verwenden?](#vcconattributeprogrammmingfaqanchor5)

- [Wie kann ich eine IDL-Datei in einem attributierten Projekt verwenden?](#vcconattributeprogrammmingfaqanchor6)

- [Kann ich Code ändern, die von einem Attribut eingefügt wird?](#vcconattributeprogrammmingfaqanchor7)

- [Wie kann ich eine Schnittstelle mit Attributen vorwärts deklarieren?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)

- [Kann ich verwenden Attribute für eine Klasse, die von einer Klasse, die Attribute auch verwendet abgeleitet?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)

##  <a name="vcconattributeprogrammmingfaqanchor1"></a> Was ist ein HRESULT?

Ein HRESULT ist ein einfacher Datentyp, der häufig als Rückgabewert von Attributen und ATL im Allgemeinen verwendet wird. Die folgende Tabelle beschreibt die verschiedenen Werte. Weitere Werte sind in den Header-Datei "Winerror.h" enthalten.

|Name|Beschreibung|Wert|
|----------|-----------------|-----------|
|S_OK|Vorgang erfolgreich|0x00000000|
|E_UNEXPECTED|Unerwarteter Fehler|0x8000FFFF|
|E_NOTIMPL|Nicht implementiert.|0x80004001|
|E_OUTOFMEMORY|Fehler beim belegen von ausreichend Arbeitsspeichers|0x8007000E|
|E_INVALIDARG|Ein oder mehrere Argumente sind ungültig|0x80070057|
|E_NOINTERFACE|Schnittstelle nicht unterstützt|0x80004002|
|E_POINTER|Ungültiger Zeiger|0x80004003|
|E_HANDLE|Ungültiges handle|0x80070006|
|E_ABORT|Vorgang wurde abgebrochen|0x80004004|
|E_FAIL|Nicht angegebener Fehler.|0x80004005|
|E_ACCESSDENIED|Allgemeiner Zugriffsfehler|0x80070005|

##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Wenn habe ich den Parameternamen für ein Attribut angeben?

In den meisten Fällen Wenn das Attribut auf einen einzelnen Parameter, hat dieser Parameter heißt. Dieser Name ist nicht erforderlich, wenn Sie das Attribut in Ihrem Code einfügen. Z. B. die folgende Syntax, der die [aggregierbaren](aggregatable.md) Attribut:

```cpp
[coclass, aggregatable(value=allowed)]
class CMyClass
{
// The class declaration
};
```

ist genau identisch:

```cpp
[coclass, aggregatable(allowed)]
class CMyClass
{
// The class declaration
};
```

Die folgenden Attribute haben jedoch eine einzelne, unbenannte Parameter:

||||
|-|-|-|
|[call_as](call-as.md)|[case](case-cpp.md)|[cpp_quote](cpp-quote.md)|
|[default](default-cpp.md)|[defaultvalue](defaultvalue.md)|[defaultvtable](defaultvtable.md)|
|[emitidl](emitidl.md)|[entry](entry.md)|[first_is](first-is.md)|
|[helpcontext](helpcontext.md)|[helpfile](helpfile.md)|[helpstring](helpstring.md)|
|[helpstringcontext](helpstringcontext.md)|[helpstringdll](helpstringdll.md)|[ID](id.md)|
|[iid_is](iid-is.md)|[import](import.md)|[importlib](importlib.md)|
|[include](include-cpp.md)|[includelib](includelib-cpp.md)|[last_is](last-is.md)|
|[length_is](length-is.md)|[max_is](max-is.md)|[no_injected_text](no-injected-text.md)|
|[pointer_default](pointer-default.md)|[pragma](pragma.md)|[restricted](restricted.md)|
|[size_is](size-is.md)|[source](source-cpp.md)|[switch_is](switch-is.md)|
|[switch_type](switch-type.md)|[transmit_as](transmit-as.md)|[wire_marshal](wire-marshal.md)|

##  <a name="vcconattributeprogrammmingfaqanchor3"></a> Kann ich Kommentare in einem Attributblock verwenden?

Sie können sowohl einzeilige und mehrzeilige Kommentare in einem Attributblock verwenden. Sie können nicht jedoch entweder Format der Kommentare innerhalb der Klammern, enthält die Parameter für ein Attribut verwenden.

Folgendes ist zulässig:

```cpp
[ coclass, progid("MyClass.CMyClass.1"), /* Multiple-line
                                       comment */
   threading("both") // Single-line comment
]
```

Die folgenden nicht zulässig ist:

```cpp
[ coclass, progid("MyClass.CMyClass.1" /* Multiple-line comment */ ), threading("both" // Single-line comment)
]
```

##  <a name="vcconattributeprogrammmingfaqanchor4"></a> Wie interagieren Attribute mit Vererbung?

Sie können sowohl attributierte Klassen von anderen Klassen erben, die selbst oder nicht zugeordnet werden kann. Das Ergebnis der Ableitung von einer attributierte Klasse ist dasselbe wie eine Ableitung von dieser Klasse nach Attributanbieter seinen Code umgewandelt hat. Attribute werden nicht auf abgeleitete Klassen durch Vererbung von C++ übertragen. Einem Attributanbieter transformiert nur Code ausgetreten ist, dessen Attribute.

##  <a name="vcconattributeprogrammmingfaqanchor5"></a> Wie kann ich die Attribute in einem nicht attributierte ATL-Projekt verwenden?

Möglicherweise ein nicht attributierte ATL-Projekt, das verfügt über eine IDL-Datei, und starten attributierter Objekte hinzufügen möchten. In diesem Fall verwenden Sie die **Assistenten zum Hinzufügen von Klasse** auf den Code bereitstellen.

##  <a name="vcconattributeprogrammmingfaqanchor6"></a> Wie kann ich eine IDL-Datei in einem attributierten Projekt verwenden?

Sie möglicherweise eine IDL-Datei, die Sie in Ihrem attributierten ATL-Projekt verwenden möchten. In diesem Fall würden Sie verwenden die [Importidl](importidl.md) Attribut, kompilieren Sie die IDL-Datei in eine .h-Datei (finden Sie unter den [Eigenschaftenseiten "MIDL"](../../build/reference/midl-property-pages.md) des Projekts **Eigenschaftenseiten** Dialogfeld), und Schließen Sie dann die .h-Datei in Ihr Projekt.

##  <a name="vcconattributeprogrammmingfaqanchor7"></a> Kann ich Code ändern, die von einem Attribut eingefügt wird?

Einige Attribute fügen Code in Ihr Projekt. Sie können den eingefügten Code anzeigen, indem Sie mit der [/FX](../../build/reference/fx-merge-injected-code.md) -Compileroption. Es ist auch möglich, Code aus der eingefügten Datei kopieren und fügen ihn in Ihren Quellcode. Dadurch können Sie das Verhalten des Attributs zu ändern. Allerdings müssen Sie möglicherweise andere Teile Ihres Codes auch ändern.

Im folgenden Beispiel wird das Ergebnis des eingefügten Code in einer Quellcodedatei kopieren:

```cpp
// attr_injected.cpp
// compile with: comsupp.lib
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name="MyLibrary") ];

// ITestTest
[
   object, uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"), dual, helpstring("ITestTest Interface"), pointer_default(unique)
]

__interface ITestTest : IDispatch {
   [id(1), helpstring("method DoTest")]
   HRESULT DoTest([in] BSTR str);
};

// _ITestTestEvents
[
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"), dispinterface, helpstring("_ITestTestEvents Interface")
]

__interface _ITestTestEvents {
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);
};

// CTestTest
[
   coclass, threading(apartment), vi_progid("TestATL1.TestTest"), progid("TestATL1.TestTest.1"), version(1.0), uuid("D9632007-14FA-4679-9E1C-28C9A949E784"), // this line would be commented out from original file
   // event_source("com"), // this line would be added to support injected code
   source(_ITestTestEvents), helpstring("TestTest Class")
]

class ATL_NO_VTABLE CTestTest : public ITestTest,
// the following base classes support added injected code
public IConnectionPointContainerImpl<CTestTest>,
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>
{
public:
   CTestTest() {
   }
   // this line would be commented out from original file
   // __event __interface _ITestTestEvents;
   DECLARE_PROTECT_FINAL_CONSTRUCT()
   HRESULT FinalConstruct() {
      return S_OK;
   }

void FinalRelease() {}

public:
   CComBSTR m_value;
   STDMETHOD(DoTest)(BSTR str) {
      VARIANT_BOOL bCancel = FALSE;
      BeforeChange(str,&bCancel);
      if (bCancel) {
          return Error("Error : Someone don't want us to change the value");
      }

   m_value =str;
   return S_OK;
    }
// the following was copied in from the injected code.
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {
   HRESULT hr = S_OK;
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;
   VARIANT rgvars[2];
   Lock();
   IUnknown** pp = p->m_vec.begin();
   Unlock();
   while (pp < p->m_vec.end()) {
      if (*pp != NULL) {
         IDispatch* pDispatch = (IDispatch*) *pp;
         ::VariantInit(&rgvars[1]);
         rgvars[1].vt = VT_BSTR;
         V_BSTR(&rgvars[1])= (BSTR) i1;
         ::VariantInit(&rgvars[0]);
         rgvars[0].vt = (VT_BOOL | VT_BYREF);
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };
         VARIANT ret_val;
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);
         if (FAILED(hr))
            break;
      }
      pp++;
   }
   return hr;
}

BEGIN_CONNECTION_POINT_MAP(CTestTest)
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))
END_CONNECTION_POINT_MAP()
// end added code section

// _ITestCtrlEvents Methods
public:
};

int main() {}
```

##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Wie kann ich eine Schnittstelle mit Attributen vorwärts deklarieren?

Wenn Sie eine Vorwärtsdeklaration einer Schnittstelle mit Attributen vornehmen möchten, müssen Sie auf der Vorwärtsdeklaration, die auf der tatsächlichen Schnittstellendeklaration angewendet, die die gleichen Attribute anwenden. Sie müssen auch anwenden, die [exportieren](export.md) -Attribut auf Ihr Vorwärtsdeklaration.

##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Kann ich verwenden Attribute für eine Klasse, die von einer Klasse, die Attribute auch verwendet abgeleitet?

Verwenden von Attributen für eine Klasse, die von einer Klasse, die Attribute auch verwendet abgeleitet ist Nein, nicht unterstützt.

## <a name="see-also"></a>Siehe auch

[C++-Attribute für COM und .NET](cpp-attributes-com-net.md)