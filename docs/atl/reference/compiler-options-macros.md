---
title: Compileroptionen Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- _ATL_ALL_WARNINGS
- _ATL_APARTMENT_THREADED
- '_ATL_CSTRING_EXPLICIT_CONSTRUCTORS '
- _ATL_ENABLE_PTM_WARNING
- _ATL_FREE_THREADED
- _ATL_MULTI_THREADED
- _ATL_NO_AUTOMATIC_NAMESPACE
- _ATL_NO_COM_SUPPORT
- ATL_NO_VTABLE
- ATL_NOINLINE
- _ATL_SINGLE_THREADED
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e84c92e8bbf65ff3b8b54111bcce2306628edb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365852"
---
# <a name="compiler-options-macros"></a>Compileroptionen Makros
Diese Makros steuern bestimmte Compilerfunktionen an.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Ein Symbol, das die Fehler in Projekten von früheren Versionen von ATL konvertiert ermöglicht|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen verwenden.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Macht bestimmte `CString` Konstruktoren explizit ist, wird verhindert, dass alle unbeabsichtigten Konvertierungen.|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Definieren Sie dieses Makro, um C++-standard kompatibel Syntax, zu verwenden, die der Compiler C4867-Fehler generiert, wenn eine nicht standardmäßige Syntax verwendet wird, um einen Zeiger auf eine Memberfunktion zu initialisieren.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Definieren Sie, wenn eine oder mehrere der Objekte frei oder neutrale threading verwenden.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Ein Symbol, das das Projekt angibt, müssen Objekte, die als sowohl "," Free "oder" Neutral gekennzeichnet sind. Das Makro [_ATL_FREE_THREADED](#_atl_free_threaded) sollte stattdessen verwendet werden.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Ein Symbol wird verhindert, dass die standardmäßige Verwendung des Namespace als ATL|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Ein Symbol, das verhindert, dass die COM-bezogenen Code kompiliert wird, während das Projekt.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Ein Symbol, das verhindert, dass die Vtable-Zeiger, die im Konstruktor und Destruktor der Klasse initialisiert wird.|  
|[ATL_NOINLINE](#atl_noinline)|Ein Symbol, das eine Funktion angibt, sollte nicht inline gesetzt werden.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Definieren Sie, wenn alle Objekte der einzelne Threadingmodell verwenden.|  
  
##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS  
 Ein Symbol, das die Fehler in Projekten von früheren Versionen von ATL konvertiert ermöglicht  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Hinweise  
 Vor Visual C++ .NET 2002 ATL viele Warnungen deaktiviert, und belassen sie deaktiviert, sodass sie nie im Benutzercode angezeigt. Dies gilt insbesondere in folgenden Fällen:  
  
-   C4127 bedingter Ausdruck ist konstant  
  
-   C4786 'Bezeichner': Bezeichner wurde auf 'Anzahl' Zeichen in den Debuginformationen gekürzt  
  
-   C4201 nicht dem Standard entsprechende Erweiterung: namenlosen Struktur/Union  
  
-   C4103 generiert 'Dateiname': verwendet #pragma Pack zum Ändern der Ausrichtung  
  
-   C4291 'Declaration': keine übereinstimmenden Delete-Operator gefunden; Speicher wird nicht freigegeben werden, wenn die Initialisierung eine Ausnahme auslöst.  
  
-   C4268 'Bezeichner': 'const' statischen/globalen Daten vom Compiler generierten Standardkonstruktor initialisiert füllt das Objekt mit Nullen  
  
-   Unerreichbarer Code C4702  
  
 In Projekten, die aus früheren Versionen konvertiert werden sind diese Warnungen noch die Bibliotheken Header deaktiviert.  
  
 Die folgende Zeile der Datei "stdafx.h" vor dem Einfügen von Bibliotheken Header hinzufügen, kann dieses Verhalten geändert werden.  
  
 [!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 Wenn diese `#define` wird zuerst hinzugefügt, die ATL-Header werden Sie darauf achten, den Status dieser Warnungen beizubehalten, damit sie nicht global deaktiviert werden (oder wenn der Benutzer explizit, Warnungen deaktiviert, nicht, um ihnen zu ermöglichen).  
  
 Neue Projekte verfügen über diese `#define` standardmäßig in "stdafx.h" festgelegt.  
  
##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED  
 Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen verwenden.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt an, Apartmentthreading für Anwendungen. Finden Sie unter [angeben des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md) für andere threading-Optionen und [Optionen, ATL-Assistent für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modelle für eine ATL-Objekt.  
  
##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 Macht bestimmte `CString` Konstruktoren explizit ist, wird verhindert, dass alle unbeabsichtigten Konvertierungen.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dies definiert ist, werden alle CString-Konstruktoren, die einen einzelnen Parameter mit dem explicit-Schlüsselwort kompiliert wird verhindert, dass bei der implizite Konvertierungen mit Eingabeargumenten. Dies bedeutet beispielsweise, dass beim _UNICODE definiert ist, wenn Sie versuchen eine Char * Zeichenfolge als Argument ein CString-Konstruktor, ein Compilerfehler führt. Verwenden Sie dieses Makro in Situationen, in denen Sie verhindern implizite Konvertierungen zwischen Zeichenfolgen für schmale und breitzeichenfolgen Datentypen müssen.  
  
 _T-Makro wird in alle Konstruktorargumente Zeichenfolge verwenden, können Sie definieren _ATL_CSTRING_EXPLICIT_CONSTRUCTORS und vermeiden Sie Kompilierungsfehler, unabhängig davon, ob _UNICODE definiert ist.  
  
##  <a name="_atl_enable_ptm_warning"></a>  _ATL_ENABLE_PTM_WARNING  
 Definieren Sie dieses Makro, um die Verwendung der ANSI C++-Standard-kompatible Syntax für Zeiger auf Memberfunktionen erzwingen. Verwenden dieses Makro wird dazu führen, dass der Compilerfehler C4867 generiert werden, wenn nicht standardmäßige Syntax verwendet wird, um einen Zeiger auf eine Memberfunktion zu initialisieren.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Hinweise  
 ATL- und MFC-Bibliotheken wurden der Visual C++-Compilers verbesserte standard C++-Kompatibilität entsprechend geändert. Gemäß dem Standard ANSI C++ muss die Syntax eines Zeigers auf eine Klassenmemberfunktion `&CMyClass::MyFunc`.  
  
 Wenn [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) ist nicht definiert (Standardfall) ATL-/MFC deaktiviert den C4867-Fehler im Makro-Zuordnungen (insbesondere meldungszuordnungen), sodass Code, der in früheren Versionen erstellt wurde, erstellen Sie wie zuvor fortgesetzt werden kann. Wenn Sie definieren **_ATL_ENABLE_PTM_WARNING**, Codes sollte die C++-Standard kompatibel sein.  
  
 Allerdings ist nicht standardmäßigen Form veraltet daher Sie vorhandenen Code in C++-standard-kompatible-Syntax zu verschieben müssen. Beispielsweise Folgendes:  
  
 [!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 Sollte geändert werden:  
  
 [!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 Beachten Sie, dass für ereigniszuordnungs-Makros, die das Zeichen "&" hinzufügen, Sie nicht wieder in Ihrem Code hinzugefügt soll.  
  
##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED  
 Definieren Sie, wenn eine oder mehrere der Objekte frei oder neutrale threading verwenden.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt an, Freethreadings. Freethreadings ist gleichbedeutend mit einem multithread Apartmentmodell. Finden Sie unter [angeben des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md) für andere threading-Optionen und [Optionen, ATL-Assistent für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modelle für eine ATL-Objekt.  
  
##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED  
 Ein Symbol, das das Projekt angibt, müssen Objekte, die als sowohl "," Free "oder" Neutral gekennzeichnet sind.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Symbol definiert ist, wird ATL Code einziehen, die Zugriff auf die globalen Daten ordnungsgemäß synchronisiert. Neue Code sollte das entsprechende Makro verwenden [_ATL_FREE_THREADED](#_atl_free_threaded) stattdessen.  
  
##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE  
 Ein Symbol wird verhindert, dass die standardmäßige Verwendung des Namespace als ATL  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Symbol nicht definiert ist, einschließlich atlbase.h führt **mit ATL-Namespace** standardmäßig die zu Namenskonflikten führen. Um dies zu verhindern, definieren Sie dieses Symbol.  
  
##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT  
 Ein Symbol, das verhindert, dass die COM-bezogenen Code kompiliert wird, während das Projekt.  
  
```
_ATL_NO_COM_SUPPORT```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 A symbol that prevents the vtable pointer from being initialized in the class's constructor and destructor.  
  
```
ATL_NO_VTABLE
```  
  
### Remarks  
 If the vtable pointer is prevented from being initialized in the class's constructor and destructor, the linker can eliminate the vtable and all of the functions to which it points. Expands to **__declspec(novtable)**.  
  
### Example  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 A symbol that indicates a function should not be inlined.  
  
```
    ATL_NOINLINE inline
    myfunction
 { ... }
```  
  
### Parameters  
 *myfunction*  
 The function that should not be inlined.  
  
### Remarks  
 Use this symbol if you want to ensure a function does not get inlined by the compiler, even though it must be declared as inline so that it can be placed in a header file. Expands to **__declspec(noinline)**.  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 Define if all of your objects use the single threading model  
  
```
_ATL_SINGLE_THREADED
```  
  
### Remarks  
 Specifies that the object always runs in the primary COM thread. See [Specifying the Project's Threading Model](../../atl/specifying-the-threading-model-for-a-project-atl.md) for other threading options, and [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) for a description of the threading models available for an ATL object.  
  
## See Also  
 [Macros](../../atl/reference/atl-macros.md)
