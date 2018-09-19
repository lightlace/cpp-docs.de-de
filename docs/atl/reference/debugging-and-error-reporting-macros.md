---
title: Debuggen und Fehlerberichterstattungs-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
dev_langs:
- C++
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fc187cea874d16522955dcd46c2ceac34d29098
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136158"
---
# <a name="debugging-and-error-reporting-macros"></a>Debuggen und Fehlerberichterstattungs-Makros

Diese Makros stellen nützliche Funktionen zum Debuggen und Ablaufverfolgung bereit.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Schreibt, in das Ausgabefenster, eine Schnittstelle Speicherverlusten, die erkannt werden, wenn `_Module.Term` aufgerufen wird.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Schreibt alle Aufrufe von `QueryInterface` im Ausgabefenster.|
|[ATLASSERT](#atlassert)|Führt die gleiche Funktionalität wie die [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Makro finden Sie in der C-Laufzeitbibliothek.|
|[ATLENSURE](#atlensure)|Überprüft die Parameter. Rufen Sie `AtlThrow` bei Bedarf|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Sendet eine Nachricht auf dem Sicherungsmedium, dass die angegebene Funktion nicht implementiert wird.|
|[ATLTRACE](#alttrace)|Gibt die Warnungen an, die ein Ausgabegerät, z. B. Debuggerfenster, entsprechend der angegebenen Flags und Ebenen. Aus Gründen der Abwärtskompatibilität enthalten.|
|[ATLTRACE2](#atltrace2)|Gibt die Warnungen an, die ein Ausgabegerät, z. B. Debuggerfenster, entsprechend der angegebenen Flags und Ebenen.|

##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES

Dieses Makro definieren, bevor alle ATL-Headerdateien, um alle verfolgen einschließen `AddRef` und `Release` aufruft, die auf Ihre Komponenten Schnittstellen im Ausgabefenster.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Hinweise

Die Ausgabe der Ablaufverfolgung wird angezeigt, wie unten dargestellt:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Der erste Teil der einzelnen ablaufverfolgungen werden immer `ATL: QIThunk`. Als Nächstes ist ein Wert, der Identifizierung der entsprechenden *Schnittstelle Thunk* verwendet wird. Ein Thunk Schnittstelle handelt es sich um ein Objekt, das verwendet, um einen Verweiszähler verwalten, und geben Sie die hier verwendete Funktionen zur Ablaufverfolgung. Ein neue Schnittstelle Thunk wird erstellt, bei jedem Aufruf von `QueryInterface` mit Ausnahme von Anforderungen für die `IUnknown` Schnittstelle (in diesem Fall der gleiche Thunk zurückgegeben jedes Mal zur Einhaltung der Regeln für COM Identität).

Als Nächstes sehen Sie `AddRef` oder `Release` , der angibt, welche Methode aufgerufen wurde. Danach sehen Sie einen Wert zur Identifizierung des Objekts, dessen Verweiszähler für Schnittstellen geändert wurde. Der Wert wird nachverfolgt, ist die **dies** -Zeiger des Objekts.

Die Anzahl der Verweise, die eine Ablaufverfolgung ausgeführt wird wird der Verweiszähler auf, Thunk nach `AddRef` oder `Release` aufgerufen wurde. Beachten Sie, dass diese Verweiszähler den Verweiszähler für das Objekt möglicherweise nicht übereinstimmt. Jede Thunk verwaltet einen eigenen Verweiszähler, damit Sie vollständig von der COM referenzzählung Regeln einhalten können.

Das letzte Teil der Informationen ist der Name des Objekts und der Schnittstelle von betroffen sind der `AddRef` oder `Release` aufrufen.

Eine Schnittstelle Verluste, die erkannt werden, wenn der Server heruntergefahren und `_Module.Term` aufrufen angemeldet sein, wie folgt:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Die bereitgestellten Informationen hier die Informationen in der vorherigen Ablaufverfolgungs-Anweisungen direkt zugeordnet, sodass Sie untersuchen können, den Verweiszähler während der gesamten Lebensdauer einer Schnittstelle Thunk. Darüber hinaus erhalten Sie einen Überblick über die maximale Anzahl von Verweisen auf diese Schnittstelle Thunk.

> [!NOTE]
> _ATL_DEBUG_INTERFACES kann in Verkaufsversionen verwendet werden.

##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI

Schreibt alle Aufrufe von `QueryInterface` im Ausgabefenster.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Hinweise

Wenn ein Aufruf von `QueryInterface` fehlgeschlagen ist, wird im Ausgabefenster angezeigt:

*Schnittstellenname* - `failed`

##  <a name="atlassert"></a>  ATLASSERT

Das Makro ATLASSERT führt die gleiche Funktionalität wie die [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Makro finden Sie in der C-Laufzeitbibliothek.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck*<br/>
Ausdruck (einschließlich Zeiger), der ungleich NULL oder 0 ergibt.

### <a name="remarks"></a>Hinweise

In Debugbuilds ATLASSERT wertet *boolescher Ausdruck* und erzeugt einen Debugbericht, wenn das Ergebnis "false" ist.  

## <a name="requirements"></a>Anforderungen

**Header:** atldef.h

##  <a name="atlensure"></a>  ATLENSURE

Dieses Makro wird verwendet, um die Parameter an eine Funktion übergeben.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck*<br/>
Gibt einen booleschen Ausdruck getestet werden.

*HR*<br/>
Gibt den Fehlercode zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Makros bieten einen Mechanismus zum Erkennen und Benachrichtigen des Benutzers der Verwendung der falsche Parameter an.

Das Makro aufruft, ATLASSERT und wenn die Bedingung Aufrufe nicht `AtlThrow`.

Im Fall ATLENSURE `AtlThrow` mit E_FAIL aufgerufen wird.

Im Fall ATLENSURE_THROW `AtlThrow` mit den angegebenen HRESULT-Wert aufgerufen wird.

Der Unterschied zwischen ATLENSURE und ATLASSERT ist ATLENSURE in Releasebuilds auch, wie in Debugbuilds löst eine Ausnahme aus.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>Anforderungen

**Header:** afx.h  

##  <a name="atltracenotimpl"></a>  ATLTRACENOTIMPL

In Debugbuilds von ATL, sendet die Zeichenfolge " *Funcname* ist nicht implementiert" auf das Sicherungsmedium und gibt E_NOTIMPL zurück.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>Parameter

*Funktionsname*<br/>
[in] Eine Zeichenfolge, die mit dem Namen der Funktion, die nicht implementiert ist.

### <a name="remarks"></a>Hinweise

Gibt in Releasebuilds einfach E_NOTIMPL zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** atltrace.h 

##  <a name="atltrace"></a>  ATLTRACE

Gibt die Warnungen an, die ein Ausgabegerät, z. B. Debuggerfenster, entsprechend der angegebenen Flags und Ebenen. Aus Gründen der Abwärtskompatibilität enthalten.

```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>Parameter

*exp*<br/>
[in] Die Zeichenfolge und die Variablen, um das Senden an das Ausgabefenster von Visual C++ oder jede Anwendung, die diese Nachrichten erfasst.

*category*<br/>
[in] Der Typ eines Ereignisses oder einer Methode auf dem Bericht. Finden Sie unter den Hinweisen für eine Liste der Kategorien.

*level*<br/>
[in] Die Ebene der Ablaufverfolgung zu Bericht. Finden Sie unter den Hinweisen zu den Details.

*lpszFormat*<br/>
[in] Die formatierte Zeichenfolge dem Sicherungsmedium an.

### <a name="remarks"></a>Hinweise

Finden Sie unter [ATLTRACE2](#atltrace2) eine Beschreibung der ATLTRACE. ATLTRACE und ATLTRACE2 weisen das gleiche Verhalten, ATLTRACE wird aus Gründen der Abwärtskompatibilität.

##  <a name="atltrace2"></a>  ATLTRACE2

Gibt die Warnungen an, die ein Ausgabegerät, z. B. Debuggerfenster, entsprechend der angegebenen Flags und Ebenen.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```

### <a name="parameters"></a>Parameter

*exp*<br/>
[in] Die Zeichenfolge, die Senden an das Ausgabefenster von Visual C++ oder jede Anwendung, die diese Nachrichten erfasst.

*category*<br/>
[in] Der Typ eines Ereignisses oder einer Methode auf dem Bericht. Finden Sie unter den Hinweisen für eine Liste der Kategorien.

*level*<br/>
[in] Die Ebene der Ablaufverfolgung zu Bericht. Finden Sie unter den Hinweisen zu den Details.

*lpszFormat*<br/>
[in] Die `printf`-style-Formatzeichenfolge verwenden, um eine Zeichenfolge, an dem Sicherungsmedium zu erstellen.

### <a name="remarks"></a>Hinweise

Die Kurzform der ATLTRACE2 schreibt eine Zeichenfolge, die im Debugger das Fenster "Ausgabe". Die zweite Form der ATLTRACE2 ebenfalls schreibt die Ausgabe in das Ausgabefenster des Debuggers, jedoch gelten die Einstellungen des Ablaufverfolgungstools ATL-/MFC (finden Sie unter [ATLTraceTool-Beispiel](../../visual-cpp-samples.md)). Wenn Sie festlegen, z. B. *Ebene* 4 und die ATL/MFC-Ablaufverfolgungstool auf Ebene 0, werden Sie nicht die Meldung angezeigt. *Ebene* kann 0, 1, 2, 3 oder 4 sein. Die Standardeinstellung 0 (null) gibt nur die schwerwiegendsten Probleme.

Die *Kategorie* Parameterlisten die Ablaufverfolgungsflags festgelegt. Diese Flags entsprechen den Typen von Methoden, die für die Sie melden möchten. Die folgenden Tabellen enthalten die gültige Ablaufverfolgungsflags Sie können die *Kategorie* Parameter.

### <a name="atl-trace-flags"></a>ATL Trace-Flags

|ATL-Kategorie|Beschreibung|
|------------------|-----------------|
|`atlTraceGeneral`|Meldet alle ATL-Anwendungen. Der Standardwert.|
|`atlTraceCOM`|Berichte zu COM-Methoden.|
|`atlTraceQI`|Berichte zu QueryInterface aufrufen.|
|`atlTraceRegistrar`|Berichte für die Registrierung von Objekten.|
|`atlTraceRefcount`|Berichte zu den Verweiszähler zu ändern.|
|`atlTraceWindowing`|Berichte zu Windows-Methoden Beispiel: Gibt eine ungültige Nachrichten-ID|
|`atlTraceControls`|Berichte für Steuerelemente Beispielsweise wird berichtet, wenn ein Steuerelement oder das Fenster zerstört wird.|
|`atlTraceHosting`|Berichten, die Meldungen hosten. Beispielsweise wird berichtet, wenn ein Client in einem Container aktiviert wird.|
|`atlTraceDBClient`|Berichte für OLE DB-Consumervorlagen Beispielsweise kann bei einem Aufruf GetData ein Fehler auftritt, die Ausgabe den HRESULT-Wert enthalten.|
|`atlTraceDBProvider`|Berichte in der Vorlage für OLE DB-Anbieter meldet z.B., wenn Fehler beim Erstellen einer Spalte.|
|`atlTraceSnapin`|Berichte für MMC-Snap-in-Anwendung.|
|`atlTraceNotImpl`|Meldet, dass die angegebene Funktion nicht implementiert wird.|
|`atlTraceAllocation`|Gibt Nachrichten, die durch den Arbeitsspeicher, die Debuggingtools in atldbgmem.h gedruckt.|

### <a name="mfc-trace-flags"></a>MFC-Ablaufverfolgungsflags

|MFC-Kategorie|Beschreibung|
|------------------|-----------------|
|`traceAppMsg`|Typ "Allgemein" MFC-Meldungen. Grundsätzlich empfohlen.|
|`traceDumpContext`|Nachrichten von [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|
|`traceWinMsg`|Nachrichten aus MFC Nachricht, die Verarbeitung von Code.|
|`traceMemory`|Nachrichten von MFC Speicher-Management-Code.|
|`traceCmdRouting`|Nachrichten von MFC Windows-Befehl, routing Code.|
|`traceHtml`|Nachrichten von MFC DHTML-Dialogfeld Unterstützung.|
|`traceSocket`|Nachrichten von MFC Socket-Unterstützung.|
|`traceOle`|Nachrichten von MFC OLE-Unterstützung.|
|`traceDatabase`|Nachrichten aus MFCs-datenbankunterstützung.|
|`traceInternet`|Nachrichten aus MFC Internet unterstützen.|

Um eine benutzerdefinierte Ablaufverfolgungskategorie deklarieren zu können, deklarieren Sie eine globale Instanz des der `CTraceCategory` -Klasse wie folgt:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Der Kategoriename, MY_CATEGORY in diesem Beispiel ist der Name, die Sie, um angeben die *Kategorie* Parameter. Der erste Parameter ist, den Namen der Kategorie, der in den ATL-/MFC-Ablaufverfolgungstool angezeigt werden. Der zweite Parameter ist der Standard-Ablaufverfolgungsebene. Dieser Parameter ist optional, und die standardmäßigen Ablaufverfolgungsebene ist 0.

So verwenden Sie eine benutzerdefinierte Kategorie:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

Um anzugeben, dass die Meldungen zur Ablaufverfolgung gefiltert werden soll, legen Sie Definitionen für diese Makros in "stdafx.h", bevor Sie die `#include <atlbase.h>` Anweisung.

Alternativ können Sie den Filter festlegen, in die Präprozessordirektiven in das **Eigenschaftenseiten** Dialogfeld. Klicken Sie auf die **Präprozessor** Registerkarte, und fügen Sie dann auf die globale in die **Präprozessordefinitionen** "Bearbeiten".

Atlbase.h enthält Default-Definitionen der Makros ATLTRACE2 aus, und diese Definitionen verwendet werden, wenn Sie nicht diese Symbole definieren, bevor atlbase.h verarbeitet wird.

In Releasebuilds kompiliert ATLTRACE2 in `(void) 0`.

ATLTRACE2 schränkt den Inhalt der Zeichenfolge, die auf dem Sicherungsmedium auf nicht mehr als 1023 Zeichen nach der Formatierung gesendet werden.

ATLTRACE und ATLTRACE2 weisen das gleiche Verhalten, ATLTRACE wird aus Gründen der Abwärtskompatibilität.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)<br/>
[Debuggen und globale Funktionen für die Fehlerberichterstattung](../../atl/reference/debugging-and-error-reporting-global-functions.md)
