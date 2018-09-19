---
title: Compileroptionen-Makros | Microsoft-Dokumentation
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
ms.openlocfilehash: 63fa47f4237d27cb8e0d5629e2041244ab360132
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075097"
---
# <a name="compiler-options-macros"></a>Compileroptionen-Makros

Diese Makros anrufsteuerungsfeatures, bestimmten Compiler.

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Symbol, das Fehler in konvertiert, die von früheren Versionen von ATL-Projekten aktiviert|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen verwenden.|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Stellt bestimmte `CString` Konstruktoren, die explizit ist, wird eine unbeabsichtigte Konvertierung verhindern.|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Definieren Sie dieses Makro, um C++ standard-kompatible Syntax, zu verwenden, die den Compilerfehler C4867 generiert, wenn eine nicht standardmäßige Syntax verwendet wird, um einen Zeiger auf eine Memberfunktion zu initialisieren.|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Wenn eine oder mehrere der Objekte frei oder neutrale threading verwenden, definieren.|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Ein Symbol, der das Projekt angibt, müssen Objekte, die als auch "," Free "oder" Neutral gekennzeichnet sind. Das Makro [_ATL_FREE_THREADED](#_atl_free_threaded) sollte stattdessen verwendet werden.|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Symbol, das verhindert, die standardmäßige Verwendung des Namespace als ATL dass|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Symbol, das verhindert, dass die COM-bezogenem Code mit Ihrem Projekt kompiliert wird.|
|[ATL_NO_VTABLE](#atl_no_vtable)|Ein Symbol, das verhindert, dass den Vtable-Zeiger, die im Konstruktor und Destruktor der Klasse initialisiert wird.|
|[ATL_NOINLINE](#atl_noinline)|Ein Symbol, das zeigt, an eine Funktion darf nicht inline sein.|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Wenn alle Ihre Objekte verwenden Sie die einzelne threading-Modell definieren.|

##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS

Symbol, das Fehler in konvertiert, die von früheren Versionen von ATL-Projekten aktiviert

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>Hinweise

Vor Visual C++ .NET 2002 ATL viele Warnungen deaktiviert und bleibt sie deaktiviert, sodass sie nicht im Benutzercode angezeigt. Dies gilt insbesondere in folgenden Fällen:

- C4127 bedingter Ausdruck ist konstant

- C4786 'Bezeichner': Bezeichner wurde auf 'Anzahl' Zeichen in den Debuginformationen gekürzt

- C4201 nicht dem Standard entsprechende Erweiterung: namenlosen Struktur/Union

- C4103 'Dateiname': verwendet #pragma Pack zum Ändern der Ausrichtung

- C4291 'Declaration': kein zugehöriger Delete-Operator gefunden. Speicher wird nicht freigegeben werden, wenn die Initialisierung eine Ausnahme auslöst.

- C4268 'Bezeichner': 'const' statischen/globalen Daten vom Compiler generierten Standardkonstruktor initialisiert füllen das Objekt mit Nullen

- C4702 unerreichbarer code

In Projekten von früheren Versionen konvertiert werden diese Warnungen weiterhin durch die Header Bibliotheken deaktiviert.

Die folgende Zeile vor dem Einfügen von Bibliotheken, Headern der Datei "stdafx.h" hinzufügen, kann dieses Verhalten geändert werden.

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

Wenn diese `#define` hinzugefügt wird, wird die ATL-Header sind darauf achten, dass den Status dieser Warnungen zu erhalten, damit sie nicht global deaktiviert werden (oder wenn der Benutzer explizit, Warnungen deaktiviert, nicht, um ihnen zu ermöglichen).

Neue Projekte haben dies `#define` standardmäßig in "stdafx.h" festgelegt.

##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED

Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen verwenden.

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>Hinweise

Gibt an, Apartmentthreading für Anwendungen. Finden Sie unter [angeben des Projekts. Threading-Modell](../../atl/specifying-the-threading-model-for-a-project-atl.md) threading Sie für andere Optionen und [Optionen, ATL-Assistent für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modellen für ein ATL-Objekt verfügbar.

##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS

Stellt bestimmte `CString` Konstruktoren, die explizit ist, wird eine unbeabsichtigte Konvertierung verhindern.

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>Hinweise

Wenn dies definiert ist, werden alle CString-Konstruktoren, die einen einzelnen Parameter mit dem explicit-Schlüsselwort, kompiliert wird verhindert, dass bei der implizite Konvertierungen von Eingabeargumenten. Dies bedeutet beispielsweise, dass wenn _UNICODE definiert wird, wenn Sie versuchen ein Char * String als Konstruktorargument CString, ein Compilerfehler führt. Verwenden Sie dieses Makro in Situationen, in dem Sie zu verhindern, dass bei der implizite Konvertierungen zwischen Zeichenfolgen für schmale und breitzeichenfolgen Datentypen müssen.

Mit dem _T-Makro für alle Konstruktor Zeichenfolgenargumente, können Sie definieren _ATL_CSTRING_EXPLICIT_CONSTRUCTORS und vermeiden Sie Kompilierungsfehler, unabhängig davon, ob _UNICODE definiert wird.

##  <a name="_atl_enable_ptm_warning"></a>  _ATL_ENABLE_PTM_WARNING

Definieren Sie dieses Makro, um die Verwendung der ANSI C++-Standard-kompatible Syntax für Zeiger auf Memberfunktionen zu erzwingen. Mit diesem Makro führt dazu, dass der Compilerfehler C4867 generiert werden, wenn keine Standardsyntax verwendet wird, um einen Zeiger auf eine Memberfunktion zu initialisieren.

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>Hinweise

Der ATL und MFC-Bibliotheken wurden geändert, um Visual C++-Compilers verbesserte C++ Kompatibilität mit dem standard entsprechen. Entsprechend dem ANSI C++-Standard, muss die Syntax eines Zeigers auf eine Klassenmemberfunktion `&CMyClass::MyFunc`.

Wenn [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) ist nicht definiert (der Standardfall), deaktiviert ATL-/MFC den C4867 Fehler in den Makro-Zuordnungen (insbesondere meldungszuordnungen) an, sodass der Code, der in früheren Versionen erstellt wurde, erstellen Sie wie zuvor fortgesetzt werden kann. Wenn Sie definieren **_ATL_ENABLE_PTM_WARNING**, Ihr Code sollte die C++-Standard kompatibel sein.

Allerdings wurde nicht standardmäßigen Form als veraltet markiert, damit Sie vorhandenen Code in C++-konforme Standardsyntax verschieben müssen. Z. B. Folgendes:

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

Sollte geändert werden:

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

Beachten Sie, dass für die Map-Makros, die das Zeichen "&" hinzufügen, Sie dieses nicht erneut in Ihrem Code hinzufügen sollen.

##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED

Wenn eine oder mehrere der Objekte frei oder neutrale threading verwenden, definieren.

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>Hinweise

Gibt an, freies threading. Freies threading ist gleichbedeutend mit einem multithread Apartmentmodell. Finden Sie unter [angeben des Projekts. Threading-Modell](../../atl/specifying-the-threading-model-for-a-project-atl.md) threading Sie für andere Optionen und [Optionen, ATL-Assistent für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modellen für ein ATL-Objekt verfügbar.

##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED

Ein Symbol, der das Projekt angibt, müssen Objekte, die als auch "," Free "oder" Neutral gekennzeichnet sind.

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>Hinweise

Wenn dieses Symbol definiert ist, wird ATL Code abzurufen, die Zugriff auf globale Daten richtig synchronisiert. Neuer Code sollte das entsprechende Makro verwenden [_ATL_FREE_THREADED](#_atl_free_threaded) stattdessen.

##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE

Symbol, das verhindert, die standardmäßige Verwendung des Namespace als ATL dass

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>Hinweise

Wenn dieses Symbol nicht definiert ist, einschließlich atlbase.h führt **mit ATL-Namespace** standardmäßig die können dazu führen, Namenskonflikte. Um dies zu verhindern, definieren Sie dieses Symbol.

##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT

Symbol, das verhindert, dass die COM-bezogenem Code mit Ihrem Projekt kompiliert wird.

```
_ATL_NO_COM_SUPPORT
```

##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE

Ein Symbol, das verhindert, dass den Vtable-Zeiger, die im Konstruktor und Destruktor der Klasse initialisiert wird.

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>Hinweise

Wenn der Vtable-Zeiger verhindert werden, die in der Klasse, Konstruktor und Destruktor initialisiert wird, kann der Linker ausgeschlossen werden Vtable und alle Funktionen auf denen er verweist. Wird erweitert, um **__declspec(novtable)"**.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

##  <a name="atl_noinline"></a>  ATL_NOINLINE

Ein Symbol, das zeigt, an eine Funktion darf nicht inline sein.

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>Parameter

*MyFunction*<br/>
Die Funktion, die nicht inline ersetzt werden sollte.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Symbol, wenn Sie möchten, um sicherzustellen, dass es sich bei eine Funktion nicht inline durch den Compiler, erhält, auch wenn es als Inline deklariert werden muss, damit, dass es in einer Headerdatei platziert werden kann. Wird erweitert, um **__declspec(noinline)**.

##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED

Definieren Sie, wenn alle Ihre Objekte verwenden Sie die einzelne threading-Modell

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>Hinweise

Gibt an, dass das Objekt immer im primären COM-Thread ausgeführt wird. Finden Sie unter [angeben des Projekts. Threading-Modell](../../atl/specifying-the-threading-model-for-a-project-atl.md) threading Sie für andere Optionen und [Optionen, ATL-Assistent für einfache Objekte](../../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modellen für ein ATL-Objekt verfügbar.

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
