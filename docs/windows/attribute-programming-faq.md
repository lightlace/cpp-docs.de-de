---
title: "Attribute Programming FAQ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributed programming"
  - "attributes [C++], frequently asked questions"
  - "FAQs (frequently asked questions), attributed programming [C++]"
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Attribute Programming FAQ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema beantwortet die folgenden häufig gestellter Fragen:  
  
-   [Was ist ein HRESULT?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [Wann muss ich den Parameternamen für ein Attribut angegeben?](#vcconattributeprogrammmingfaqanchor2)  
  
-   [Kann ich Kommentare in einem Attributblock verwenden?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [Wie die Interaktion mit Vererbung Attribute?](#vcconattributeprogrammmingfaqanchor4)  
  
-   [Wie kann ich Attribute in einem nicht attributiertes ATL\-Projekt verwendet werden?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [Wie kann ich eine IDL\-Datei in einem attributierten Projekt verwendet werden?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [Kann ich Code ändern, in dem von einem Attribut eingefügt wurde?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [Wie kann ich weiterleiten deklariere eine attributierte Schnittstelle?](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [Kann ich Attribute für eine Klasse verwenden, die von einer Klasse abgeleitet ist, die auch Attribute verwendet werden?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> Was ist ein HRESULT?  
 `HRESULT` ist ein einfacher Datentyp, der als Rückgabewert von ATL und Attribute im Allgemeinen häufig verwendet wird.  Die folgende Tabelle beschreibt die verschiedenen Werte.  Mehrere Werte werden in der Headerdatei winerror.h enthalten.  
  
|Name|Beschreibung|Wert|  
|----------|------------------|----------|  
|S\_OK|Vorgang erfolgreich|0x00000000|  
|E\_UNEXPECTED|Unerwarteter Fehler|0x8000FFFF|  
|E\_NOTIMPL|Nicht implementiert.|0x80004001|  
|E\_OUTOFMEMORY|Fehlgeschlagene notwendigen Speicher belegen|0x8007000E|  
|E\_INVALIDARG|Eine oder mehrere Argumente sind unzulässig|0x80070057|  
|E\_NOINTERFACE|Keine dieser Schnittstelle unterstützt|0x80004002|  
|E\_POINTER|Ungültiger Zeiger|0x80004003|  
|E\_HANDLE|Ungültiges Handle|0x80070006|  
|E\_ABORT|Vorgang abgebrochen|0x80004004|  
|E\_FAIL|Fehler Nicht angegeben|0x80004005|  
|E\_ACCESSDENIED|Allgemeiner Fehler verweigerte Zugriff|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> Wann muss ich den Parameternamen für ein Attribut angegeben?  
 In den meisten Fällen wenn das Attribut über einen einzelnen Parameter verfügt, wird dieser Parameter benannt.  Dieser Name ist nicht erforderlich, wenn er das Attribut im Code einfügt.  Beispielsweise legt der folgende Verwendung des Attributs [aggregierbar](../windows/aggregatable.md) :  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 exakt entspricht:  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 Allerdings besitzen die folgenden Attribute der einzelnen unbenannten Parameter:  
  
||||  
|-|-|-|  
|[call\_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp\_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[Eingabe](../windows/entry.md)|[first\_is](../windows/first-is.md)|  
|[helpcontext](../windows/helpcontext.md)|[helpfile](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[id](../windows/id.md)|  
|[iid\_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[Einschließen](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last\_is](../windows/last-is.md)|  
|[length\_is](../windows/length-is.md)|[max\_is](../windows/max-is.md)|[no\_injected\_text](../windows/no-injected-text.md)|  
|[pointer\_default](../windows/pointer-default.md)|[Pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size\_is](../windows/size-is.md)|[source](../windows/source-cpp.md)|[switch\_is](../windows/switch-is.md)|  
|[switch\_type](../windows/switch-type.md)|[transmit\_as](../windows/transmit-as.md)|[wire\_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> Kann ich Kommentare in einem Attributblock verwenden?  
 Sie können die einzeiligen und mehrzeiligen Kommentare innerhalb eines Attributblocks verwenden.  Sie können jedoch jedes Format des Kommentars in Klammern verwenden, die die Parameter für ein Attribut enthalten.  
  
 Im Folgenden ist zulässig:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 Im Folgenden wird nicht zulässig:  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> Wie die Interaktion mit Vererbung Attribute?  
 Sie können die attributierten und unattributed Klassen von anderen Klassen erben, die möglicherweise selbst oder nicht attributiert sind.  Das Ergebnis der Berechnung von der attributierten Klasse entspricht dem die Ableitung von dieser Klasse, nach dem der Anbieter den Code Attribut umgewandelt wurde.  Attribute sind nicht auf die abgeleitete Klassen von C\+\+\-Vererbung gesendet.  Ein Attribut für Transformationen nur Code in der Nähe von ihren Attributen.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> Wie kann ich Attribute in einem nicht attributiertes ATL\-Projekt verwendet werden?  
 Sie haben möglicherweise ein nicht attributiertes ATL\-Projekt, das eine IDL\-Datei hat, und Sie sollten das Hinzufügen von attributierten Objekte beginnen.  In diesem Fall verwenden Sie den Assistenten zum Hinzufügen von Klassen, um den Code bereitzustellen.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> Wie kann ich eine IDL\-Datei in einem attributierten Projekt verwendet werden?  
 Sie haben möglicherweise eine IDL\-Datei, die Sie im attributierten Projekt ATL verwenden möchten.  In diesem Fall würden Sie das Attribut [importidl](../windows/importidl.md) Kompilieren der IDL\-Datei an eine H\-Datei \(siehe [Eigenschaftenseiten " MIDL "](../ide/midl-property-pages.md) im Dialogfeld Eigenschaftenseiten des Projekts\) einschließen und dann die H\-Datei im Projekt.  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> Kann ich Code ändern, in dem von einem Attribut eingefügt wurde?  
 Einige Attribute fügen Code in das Projekt ein.  Sie können den eingefügten Code überprüfen, indem Sie die [\/Fx](../build/reference/fx-merge-injected-code.md)\-Compileroption verwenden.  Es ist auch möglich, Code von der eingefügte Datei zu kopieren und diesen in den Quellcode eingefügt werden soll.  Dies ermöglicht es Ihnen, das Verhalten des Attributs zu ändern.  Allerdings müssen Sie möglicherweise andere Teile des Codes ändern.  
  
 Im folgenden Beispiel ist das Ergebnis des Kopierens des eingefügten Codes in einer Quellcodedatei:  
  
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
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> Wie kann ich weiterleiten deklariere eine attributierte Schnittstelle?  
 Wenn Sie eine Vorwärtsdeklaration einer Schnittstelle mit Attributen vornehmen, müssen Sie dieselben Attribute der Vorwärtsdeklaration anwenden, die Sie zur eigentlichen Schnittstellendeklaration anwenden.  Sie müssen das [export](../windows/export.md) auch Vorwärtsdeklaration Attribut anwenden.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> Kann ich Attribute für eine Klasse verwenden, die von einer Klasse abgeleitet ist, die auch Attribute verwendet werden?  
 Nein, mithilfe von Attributen für eine Klasse, die von einer Klasse abgeleitet ist, die auch Attribute verwendet, wird nicht unterstützt.  
  
## Siehe auch  
 [Concepts](../windows/attributed-programming-concepts.md)