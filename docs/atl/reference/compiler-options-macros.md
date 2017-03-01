---
title: Compileroptionen Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dbce962873194c1bdcb063537247650cff568e35
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-options-macros"></a>Compileroptionen Makros
Diese Makros steuern bestimmte Compilerfunktionen.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Symbol, das Fehler in Projekten von früheren Versionen von ATL konvertiert aktiviert|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Definieren Sie, wenn eine oder mehrere der Objekte das Apartmentthreadingmodell verwendet.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Stellt bestimmte `CString` Konstruktoren, die verhindern, dass eine unbeabsichtigte Konvertierung explizit.|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Definieren Sie dieses Makro, um C++-kompatiblen Standardsyntax verwenden, die Compilerfehler C4867 generiert, wenn eine nicht standardmäßige Syntax verwendet wird, um einen Zeiger auf eine Memberfunktion zu initialisieren.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Definieren Sie, wenn eine oder mehrere der Objekte frei oder neutrales threading verwendet.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Ein Symbol, das das Projekt angibt, müssen Objekte, die als auch "," frei "oder" Neutral markiert sind. Das Makro [_ATL_FREE_THREADED](#_atl_free_threaded) sollte stattdessen verwendet werden.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Symbol, das verhindert, die standardmäßige Verwendung des Namespaces als ATL dass|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Symbol, das verhindert, dass COM-bezogenen Code mit Ihrem Projekt kompiliert wird.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Ein Symbol, das verhindert, dass den Vtable-Zeiger im Konstruktor und Destruktor der Klasse initialisiert wird.|  
|[ATL_NOINLINE](#atl_noinline)|Ein Symbol, das eine Funktion gibt, sollte nicht inline gesetzt werden.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Definieren Sie, wenn alle Objekte der einzelne threading-Modell verwenden.|  
  
##  <a name="a-nameatlallwarningsa--atlallwarnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS  
 Symbol, das Fehler in Projekten von früheren Versionen von ATL konvertiert aktiviert  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Hinweise  
 Vor Visual C++ .NET 2002 ATL viele Warnungen deaktiviert und Links werden deaktiviert, sodass sie sich nicht im Benutzercode werden angezeigt. Dies gilt insbesondere in folgenden Fällen:  
  
-   C4127 bedingter Ausdruck ist konstant  
  
-   C4786 'Bezeichner': Bezeichner wurde auf 'Anzahl' Zeichen in den Debuginformationen gekürzt  
  
-   C4201 nicht dem Standard entsprechende Erweiterung: namenlosen Struktur/Union  
  
-   C4103 generiert "Dateiname": verwendet #pragma Pack zum Ändern der Ausrichtung  
  
-   C4291 'Deklaration': kein zugehöriger Delete-Operator gefunden; Speicher wird nicht freigegeben werden, wenn die Initialisierung eine Ausnahme auslöst.  
  
-   C4268 'Bezeichner': 'const' statische oder globale Daten, die mit dem vom Compiler generierten Standardkonstruktor initialisiert das Objekt mit Nullen gefüllt  
  
-   C4702 nicht erreichbaren code  
  
 In Projekten, die aus früheren Versionen konvertiert werden werden diese Warnungen immer noch durch die Bibliotheken Header deaktiviert.  
  
 Die folgende Zeile der Datei stdafx.h vor einschließlich Bibliotheken Header hinzufügen, kann dieses Verhalten geändert werden.  
  
 [!code-cpp[NVC_ATL_Utilities&#97;](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 Wenn diese `#define` hinzugefügt wird, wird die ATL-Header sind darauf achten, dass den Status dieser Warnungen beibehalten, damit sie nicht global deaktiviert sind (oder wenn der Benutzer explizit Warnungen, nicht, um sie zu aktivieren deaktiviert).  
  
 Neue Projekte, die mit Visual C++ .NET 2002 generiert haben dies `#define` in der Datei stdafx.h standardmäßig festgelegt.  
  
##  <a name="a-nameatlapartmentthreadeda--atlapartmentthreaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED  
 Definieren Sie, wenn eine oder mehrere der Objekte das Apartmentthreadingmodell verwendet.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Apartmentthreading. Finden Sie unter [Festlegen des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md) für andere threading-Optionen und [Optionen, ATL-Assistenten für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modelle für ein ATL-Objekt zur Verfügung.  
  
##  <a name="a-nameatlcstringexplicitconstructorsa--atlcstringexplicitconstructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 Stellt bestimmte `CString` Konstruktoren, die verhindern, dass eine unbeabsichtigte Konvertierung explizit.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dies definiert ist, werden alle CString-Konstruktoren, die einen einzelnen Parameter mit dem explicit-Schlüsselwort kompiliert wird verhindert, implizite Konvertierungen von Eingabeargumenten dass. Dies bedeutet beispielsweise, dass wenn _UNICODE definiert ist, wenn Sie versuchen Char * String als Konstruktorargument CString, ein Compilerfehler führt. Verwenden Sie dieses Makro in Situationen Sie implizite Konvertierungen zwischen Zeichenfolgentypen schmale und Breite zu verhindern müssen.  
  
 Das Makro _T in alle Konstruktor Zeichenfolgenargumente verwenden, können Sie #define _ATL_CSTRING_EXPLICIT_CONSTRUCTORS und vermeiden Sie Kompilierungsfehler, unabhängig davon, ob _UNICODE definiert ist.  
  
##  <a name="a-nameatlenableptmwarninga--atlenableptmwarning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING  
 Definieren Sie dieses Makro, um die Verwendung des ANSI C++-Standard-kompatible Syntax für Zeiger auf Memberfunktionen erzwingen. Verwenden dieses Makro führt dazu, dass den Compilerfehler C4867 generiert werden, wenn nicht standardmäßiger Syntax verwendet wird, um einen Zeiger auf eine Memberfunktion zu initialisieren.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL- und MFC-Bibliotheken wurden geändert, um verbesserte, standard C++-Kompatibilität von Visual C++-Compilers übereinstimmen. Gemäß dem Standard ANSI C++ muss die Syntax eines Zeigers auf eine Memberfunktion der Klasse `&CMyClass::MyFunc`.  
  
 Wenn [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) nicht definiert ist (die Standard-Schreibweise), ATL und MFC deaktiviert den C4867 Fehler im Makro-Zuordnungen (insbesondere meldungszuordnungen), sodass Code, der in früheren Versionen erstellt wurde, erstellen Sie wie zuvor fortgesetzt werden kann. Wenn Sie definieren **_ATL_ENABLE_PTM_WARNING**, der Code sollte die C++-Standard kompatibel sein.  
  
 Allerdings ist nicht standardmäßige Form veraltet benötigen Sie vorhandenen Code in C++-standard-kompatible-Syntax zu verschieben. Zum Beispiel Folgendes:  
  
 [!code-cpp[NVC_MFCListView&14;](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 Sollte geändert werden:  
  
 [!code-cpp[NVC_MFCListView&#11;](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 Beachten Sie, dass für Makros, die das Zeichen '&' hinzufügen, nicht es erneut in Ihrem Code hinzufügen sollten.  
  
##  <a name="a-nameatlfreethreadeda--atlfreethreaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED  
 Definieren Sie, wenn eine oder mehrere der Objekte frei oder neutrales threading verwendet.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die free-threading. Free-threading ist ein multithread Apartmentmodell entspricht. Finden Sie unter [Festlegen des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md) für andere threading-Optionen und [Optionen, ATL-Assistenten für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modelle für ein ATL-Objekt zur Verfügung.  
  
##  <a name="a-nameatlmultithreadeda--atlmultithreaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED  
 Ein Symbol, das das Projekt angibt, müssen Objekte, die als auch "," frei "oder" Neutral markiert sind.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Symbol definiert ist, wird ATL Code aufruft, die Zugriff auf die globalen Daten ordnungsgemäß synchronisiert. Neue Code sollte das entsprechende Makro verwenden [_ATL_FREE_THREADED](#_atl_free_threaded) stattdessen.  
  
##  <a name="a-nameatlnoautomaticnamespacea--atlnoautomaticnamespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE  
 Symbol, das verhindert, die standardmäßige Verwendung des Namespaces als ATL dass  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Symbol nicht definiert ist, einschließlich atlbase.h führt **mit ATL-Namespace** standardmäßig die zu Namenskonflikten führen. Um dies zu vermeiden, definieren Sie dieses Symbol.  
  
##  <a name="a-nameatlnocomsupporta--atlnocomsupport"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT  
 Symbol, das verhindert, dass COM-bezogenen Code mit Ihrem Projekt kompiliert wird.  
  
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

