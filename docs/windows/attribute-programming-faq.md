---
title: "-Attribut Programmierung – häufig gestellte Fragen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- attributed programming
- attributes [C++], frequently asked questions
- FAQs (frequently asked questions), attributed programming [C++]
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 76b7ad2c7acb9d232602c620a70cefabbecee531
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="attribute-programming-faq"></a>Fragen und Antworten zur attributierten Programmierung
In diesem Thema werden die folgenden häufig gestellten Fragen beantwortet:  
  
-   [Was ist ein HRESULT?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Wenn habe ich den Parameternamen für ein Attribut angeben?](#vcconattributeprogrammmingfaqanchor2)  
  
-   [Kann ich Kommentare in ein Attributblock verwenden?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [Wie interagieren Attribute mit Vererbung?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [Wie kann ich die Attribute in einem nicht attributierte ATL-Projekt verwenden?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [Wie kann ich eine IDL-Datei in einem attributierte Projekt verwenden?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [Kann ich Code ändern, die von einem Attribut eingeschleust wird?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [Wie kann ich eine Schnittstelle mit Attributen vorwärts deklariert?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [Kann ich verwenden Attribute einer Klasse abgeleitet wurde eine Klasse, die auch Attribute verwendet?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a>Was ist ein HRESULT?  
 Ein `HRESULT` wird von ein einfachen Datentyp, der häufig als Rückgabewert von Attributen und ATL im Allgemeinen verwendet wird. Die folgende Tabelle beschreibt die verschiedenen Werte. Weitere Werte sind in der Headerdatei winerror.h enthalten.  
  
|name|Beschreibung|Wert|  
|----------|-----------------|-----------|  
|S_OK|Vorgang erfolgreich|0x00000000|  
|E_UNEXPECTED|Unerwarteter Fehler|0x8000ffff|  
|E_NOTIMPL|Nicht implementiert.|0 x 80004001|  
|E_OUTOFMEMORY|Fehler beim belegen von Arbeitsspeicher erforderlich|0x8007000E|  
|E_INVALIDARG|Ein oder mehrere Argumente sind ungültig|0 x 80070057|  
|E_NOINTERFACE|Schnittstelle nicht unterstützt.|0 x 80004002|  
|E_POINTER|Ungültiger Zeiger|0 x 80004003|  
|E_HANDLE|Ungültiges handle|0x80070006|  
|E_ABORT|Der Vorgang wurde abgebrochen|0 x 80004004|  
|E_FAIL|Nicht angegebener Fehler|0 x 80004005|  
|E_ACCESSDENIED|Allgemeine Zugriffsfehler|0 x 80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a>Wenn habe ich den Parameternamen für ein Attribut angeben?  
 Wenn das Attribut auf einen einzelnen Parameter verfügt, wird in den meisten Fällen diesen Parameter benannt. Dieser Name ist nicht erforderlich, wenn das Attribut in den Code einfügen. Z. B. die folgende Syntax, der die [aggregierbar](../windows/aggregatable.md) Attribut:  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 ist als identisch:  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 Allerdings müssen die folgenden Attribute einzelne, unbenannte Parameter:  
  
||||  
|-|-|-|  
|[call_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[entry](../windows/entry.md)|[first_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[ID](../windows/id.md)|  
|[iid_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[include](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last_is](../windows/last-is.md)|  
|[length_is](../windows/length-is.md)|[max_is](../windows/max-is.md)|[no_injected_text](../windows/no-injected-text.md)|  
|[pointer_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size_is](../windows/size-is.md)|[Datenquelle](../windows/source-cpp.md)|[switch_is](../windows/switch-is.md)|  
|[switch_type](../windows/switch-type.md)|[transmit_as](../windows/transmit-as.md)|[wire_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a>Kann ich Kommentare in ein Attributblock verwenden?  
 Sie können einzeiligen und mehrzeiligen Kommentare in ein Attributblock verwenden. Entweder Stil der Kommentar zwischen den Klammern, halten die Parameter an ein Attribut kann nicht jedoch nicht verwendet werden.  
  
 Die folgenden zulässig:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Die folgenden nicht zulässig:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a>Wie interagieren Attribute mit Vererbung?  
 Sie können sowohl attributierte Klassen von anderen Klassen erben, die selbst oder nicht mit Attributen versehen werden kann. Das Ergebnis einer attributierte Klasse abgeleitet ist identisch mit der von dieser Klasse ableiten, nachdem der Attributanbieter des Codes umgewandelt wurde. Attribute werden nicht auf abgeleitete Klassen durch Vererbung von C++ übertragen. Ein Attributanbieter wandelt nur Code in seiner Attribute.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a>Wie kann ich die Attribute in einem nicht attributierte ATL-Projekt verwenden?  
 Müssen unter Umständen eine nicht attributierte ATL-Projekt, das eine IDL-Datei verfügt, und Sie möchten nun attributierte Objekte hinzufügen. In diesem Fall verwenden Sie den Assistenten zum Hinzufügen einer Klasse, um den Code bereitzustellen.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a>Wie kann ich eine IDL-Datei in einem attributierte Projekt verwenden?  
 Sie möglicherweise eine IDL-Datei, die Sie in Ihrem attributierten ATL-Projekt verwenden möchten. In diesem Fall würden Sie verwenden die [Importidl](../windows/importidl.md) -Attribut, kompilieren Sie die IDL-Datei in eine .h-Datei (finden Sie unter der [Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md) im Dialogfeld Eigenschaftenseiten des Projekts), und schließen Sie dann die .h-Datei in Ihrem Projekt .  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a>Kann ich Code ändern, die von einem Attribut eingeschleust wird?  
 Einige Attribute fügen Code in Ihrem Projekt. Sehen Sie den eingefügten Code mit der [/FX](../build/reference/fx-merge-injected-code.md) -Compileroption. Es ist auch möglich, Code aus der eingefügten Datei kopieren und fügen ihn in Ihren Quellcode. Dadurch können Sie das Verhalten des Attributs zu ändern. Allerdings müssen Sie möglicherweise andere Teile des Codes auch ändern.  
  
 Im folgende Beispiel ist das Ergebnis von eingefügtem Code in einer Quellcodedatei kopieren:  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
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
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a>Wie kann ich eine Schnittstelle mit Attributen vorwärts deklariert?  
 Wenn Sie eine Vorwärtsdeklaration einer Schnittstelle mit Attributen vornehmen möchten, müssen Sie auf der Vorwärtsdeklaration, die Sie für die tatsächliche Schnittstellendeklaration gelten, die dieselben Attribute anwenden. Sie müssen auch anwenden, die [exportieren](../windows/export.md) -Attribut auf die Vorwärtsdeklaration.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a>Kann ich verwenden Attribute einer Klasse abgeleitet wurde eine Klasse, die auch Attribute verwendet?  
 Nein, wird das Verwenden von Attributen für eine Klasse, die von einer Klasse, die auch Attribute verwendet abgeleitet nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../windows/attributed-programming-concepts.md)