---
title: Debuggen und die Fehlerberichterstattung Makros | Microsoft-Dokumentation
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
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 112b43c325d4b73d2cc15ba41d9aac255c74da8a
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-macros"></a>Debuggen und die Fehlerberichterstattung Makros
Diese Makros stellen nützliche Debug- und Trace-Funktionen bereit.  
  
|||  
|-|-|  
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Schreibt, im Ausgabefenster eine Schnittstelle Speicherverlusten, die erkannt werden, wenn `_Module.Term` aufgerufen wird.|  
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Schreibt alle Aufrufe von `QueryInterface` im Ausgabefenster angezeigt.|  
|[ATLASSERT](#atlassert)|Führt die gleiche Funktionalität wie die [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Makros finden Sie in der C-Laufzeitbibliothek.|  
|[ATLENSURE](#atlensure)|Führt die Überprüfung von Parametern. Rufen Sie `AtlThrow` bei Bedarf|  
|[ATLTRACENOTIMPL](#atltracenotimpl)|Sendet eine Nachricht auf dem Sicherungsmedium, dass die angegebene Funktion ist nicht implementiert.|  
|[ATLTRACE](http://msdn.microsoft.com/library/c796baa5-e2b9-4814-a27d-d800590b102e)|Meldet Warnungen an ein Ausgabegerät, wie z. B. das Debuggerfenster, gemäß der angegebenen Flags und Ebenen. Aus Gründen der Abwärtskompatibilität enthalten.|  
|[ATLTRACE2](#atltrace2)|Meldet Warnungen an ein Ausgabegerät, wie z. B. das Debuggerfenster, gemäß der angegebenen Flags und Ebenen.|  
  
##  <a name="a-nameatldebuginterfacesa--atldebuginterfaces"></a><a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES  
 Dieses Makro definieren, bevor Sie alle ATL-Headerdateien, um alle Ablaufverfolgungsinformationen einschließlich `AddRef` und **Version** Ruft für die Komponenten Schnittstellen im Ausgabefenster.  
  
```
#define _ATL_DEBUG_INTERFACES
```  
  
### <a name="remarks"></a>Hinweise  
 Die Ausgabe wird angezeigt, wie unten dargestellt:  
  
 `ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`  
  
 Der erste Teil jeder Trace werden immer `ATL: QIThunk`. Als Nächstes ist ein Wert, der Identifizierung des jeweiligen *Schnittstelle Thunk* verwendet wird. Ein Thunk Schnittstelle ist ein Objekt verwendet, um einen Verweiszähler verwalten und ermöglichen Tracing hier verwendet. Erstellt ein neue Schnittstelle Thunk bei jedem Aufruf von `QueryInterface` mit Ausnahme von Anforderungen für die **IUnknown** Schnittstelle (in diesem Fall der gleiche Thunk zurückgegeben jedes Mal auf die COM Identitätsregeln entsprechen).  
  
 Als Nächstes sehen Sie `AddRef` oder **Version** , der angibt, welche Methode aufgerufen wurde. Danach sehen Sie einen Wert zur Identifizierung des Objekts, dessen Verweiszähler geändert wurde. Der Wert wird nachverfolgt, ist die **dies** -Zeiger des Objekts.  
  
 Wird der Verweiszähler verfolgt wird, die Anzahl der Verweise auf diese Thunk nach `AddRef` oder **Version** aufgerufen wurde. Beachten Sie, dass diese Verweiszähler den Verweiszähler für das Objekt möglicherweise nicht übereinstimmen. Jede Thunk verwaltet einen eigenen Verweiszähler Hilfestellungen vollständig zählen von Verweisen von COM-Regeln entsprechen.  
  
 Verfolgt die letzte Information ist der Name des Objekts und die Schnittstelle durch den `AddRef` oder **Version** aufrufen.  
  
 Jede Schnittstelle prüfen auf Speicherverluste, die erkannt werden, wenn der Server heruntergefahren und `_Module.Term` aufrufen protokolliert werden, wie folgt:  
  
 `ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`  
  
 Informationen finden Sie hier die Informationen in der vorherigen Trace-Anweisungen direkt zugeordnet, damit Sie untersuchen können den Verweiszähler während der gesamten Lebensdauer ein Thunk Schnittstelle. Darüber hinaus erhalten Sie ein Hinweis auf die maximale Anzahl von Verweisen auf diese Schnittstelle Thunk.  
  
> [!NOTE]
> `_ATL_DEBUG_INTERFACES`kann in Retail-Builds verwendet werden.  
  
##  <a name="a-nameatldebugqia--atldebugqi"></a><a name="_atl_debug_qi"></a>_ATL_DEBUG_QI  
 Schreibt alle Aufrufe von `QueryInterface` im Ausgabefenster angezeigt.  
  
```
#define _ATL_DEBUG_QI
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Aufruf von `QueryInterface` fehlgeschlagen ist, wird im Ausgabefenster angezeigt:  
  
 *Name der Schnittstelle* - `failed`  
  
##  <a name="a-nameatlasserta--atlassert"></a><a name="atlassert"></a>ATLASSERT  
 Die `ATLASSERT` Makro führt die gleiche Funktionalität wie die [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Makros finden Sie in der C-Laufzeitbibliothek.  
  
```
ATLASSERT(booleanExpression);
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Ausdruck (einschließlich Zeiger), einen Wert ungleich NULL oder 0 ergibt.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds `ATLASSERT` ergibt `booleanExpression` und erzeugt einen Debugbericht, wenn das Ergebnis false.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldef.h  
    
##  <a name="a-nameatlensurea--atlensure"></a><a name="atlensure"></a>ATLENSURE  
 Dieses Makro wird verwendet, um die Parameter an eine Funktion übergeben.  
  
```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```  
  
### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Gibt einen booleschen Ausdruck getestet werden soll.  
  
 `hr`  
 Gibt den Fehlercode zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Makros bieten einen Mechanismus zum Erkennen und benachrichtigt den Benutzer der Verwendung falscher Parameter.  
  
 Die Makro-Aufrufe `ATLASSERT` und wenn die Bedingung Aufrufe nicht `AtlThrow`.  
  
 In der **ATLENSURE** Fall `AtlThrow` mit E_FAIL aufgerufen wird.  
  
 In der **ATLENSURE_THROW** Fall `AtlThrow` mit den angegebenen HRESULT aufgerufen wird.  
  
 Der Unterschied zwischen **ATLENSURE** und `ATLASSERT` ist, **ATLENSURE** löst eine Ausnahme in Version sowie wie Debug-Builds erstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#108;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  

##  <a name="a-nameatltracenotimpla--atltracenotimpl"></a><a name="atltracenotimpl"></a>ATLTRACENOTIMPL  
 In Debugbuilds ATL sendet die Zeichenfolge " `funcname` ist nicht implementiert" auf das Sicherungsmedium und gibt **E_NOTIMPL**.  
  
```
ATLTRACENOTIMPL(funcname);
```  
  
### <a name="parameters"></a>Parameter  
 `funcname`  
 [in] Eine Zeichenfolge mit dem Namen der Funktion, die nicht implementiert ist.  
  
### <a name="remarks"></a>Hinweise  
 Einfach in Releasebuilds gibt **E_NOTIMPL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[127 NVC_ATL_Utilities](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltrace.h 

##  <a name="a-nameatla--atltrace"></a><a name="atl_"></a>ATLTRACE
 Meldet Warnungen an ein Ausgabegerät, wie z. B. das Debuggerfenster, gemäß der angegebenen Flags und Ebenen. Aus Gründen der Abwärtskompatibilität enthalten.  
  
```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `exp`  
 [in] Die Zeichenfolge und die Variablen an das Ausgabefenster von Visual C++ oder einer Anwendung, die diese Nachrichten traps zu senden.  
  
 `category`  
 [in] Der Typ eines Ereignisses oder einer Methode auf dem Bericht. Siehe die Hinweise für eine Liste von Kategorien.  
  
 `level`  
 [in] Die Ebene der Protokollierung auf Bericht. Finden Sie weitere Informationen.  
  
 `lpszFormat`  
 [in] Die formatierte Zeichenfolge das Dump-Gerät an.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ATLTRACE2](#atltrace2) eine Beschreibung der **ATLTRACE**. **ATLTRACE** und `ATLTRACE2` weisen das gleiche Verhalten, **ATLTRACE** wird aus Gründen der Abwärtskompatibilität.  
  
##  <a name="a-nameatltrace2a--atltrace2"></a><a name="atltrace2"></a>ATLTRACE2  
 Meldet Warnungen an ein Ausgabegerät, wie z. B. das Debuggerfenster, gemäß der angegebenen Flags und Ebenen.  
  
```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```  
  
### <a name="parameters"></a>Parameter  
 `exp`  
 [in] Die Zeichenfolge zum Senden an das Ausgabefenster von Visual C++ oder einer Anwendung, die diese Nachrichten aufruft.  
  
 `category`  
 [in] Der Typ eines Ereignisses oder einer Methode auf dem Bericht. Siehe die Hinweise für eine Liste von Kategorien.  
  
 `level`  
 [in] Die Ebene der Protokollierung auf Bericht. Finden Sie weitere Informationen.  
  
 `lpszFormat`  
 [in] Die `printf`-style-Formatzeichenfolge verwenden, um eine Zeichenfolge an das Sicherungsmedium zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Die Kurzform der `ATLTRACE2` schreibt eine Zeichenfolge, die der Debugger im Fenster Ausgabe. Die zweite Form der `ATLTRACE2` schreibt die Ausgabe in der Debugger-Ausgabefenster auch die Einstellungen für die ATL-/MFC-Ablaufverfolgungsprogramm unterliegt (finden Sie unter [ATLTraceTool-Beispiel](../../visual-cpp-samples.md)). Wenn Sie festlegen, z. B. `level` 4 und die ATL-/MFC-Ablaufverfolgungsprogramm auf Ebene 0, werden Sie nicht die Meldung angezeigt. *Ebene* kann 0, 1, 2, 3 oder 4 sein. Die Standardeinstellung 0 ist, meldet nur schwerwiegenden Problemen.  
  
 Die `category` Parameterlisten Ablaufverfolgungsflags festgelegt. Diese Flags entsprechen den Typen von Methoden für die Sie einen Bericht erstellen möchten. Die folgenden Tabellen enthalten die gültigen Ablaufverfolgungsflags können Sie die `category` Parameter.  
  
### <a name="atl-trace-flags"></a>ATL-Ablaufverfolgungsflags  
  
|ATL-Kategorie|Beschreibung|  
|------------------|-----------------|  
|`atlTraceGeneral`|Meldet alle ATL-Programme. Der Standardwert.|  
|`atlTraceCOM`|Berichte zu COM-Methoden.|  
|`atlTraceQI`|Berichte über QueryInterface-Aufrufe.|  
|`atlTraceRegistrar`|Berichte über die Registrierung von Objekten.|  
|`atlTraceRefcount`|Berichte zum Ändern der Verweiszähler.|  
|`atlTraceWindowing`|Berichte zu Windows-Methoden; Beispielsweise meldet eine ungültige e-Mail-Map-ID.|  
|`atlTraceControls`|Berichte für Steuerelemente Beispielsweise wird berichtet, wenn ein Steuerelement oder das Fenster zerstört wird.|  
|`atlTraceHosting`|Berichte, die für Nachrichten; Beispielsweise wird berichtet, wenn ein Client in einem Container aktiviert ist.|  
|`atlTraceDBClient`|Berichte über OLE DB-Consumervorlagen; Beispielsweise kann bei Aufruf GetData schlägt fehl, die Ausgabe der HRESULT-Wert enthalten.|  
|`atlTraceDBProvider`|Berichten auf der Vorlage für OLE DB-Anbieter. meldet z. B., wenn Fehler bei der Erstellung einer Spalte.|  
|`atlTraceSnapin`|Berichte für MMC-Snap-in-Anwendung.|  
|`atlTraceNotImpl`|Gibt an, dass die angegebene Funktion ist nicht implementiert.|  
|**atlTraceAllocation**|Meldet die Nachrichten, die durch den Arbeitsspeicher debugging-Tools in atldbgmem.h gedruckt.|  
  
### <a name="mfc-trace-flags"></a>MFC-Ablaufverfolgungsflags  
  
|MFC-Kategorie|Beschreibung|  
|------------------|-----------------|  
|**traceAppMsg**|Allgemeine MFC-Nachrichten. Grundsätzlich empfohlen.|  
|**traceDumpContext**|Nachrichten von [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|  
|**traceWinMsg**|Nachrichten von Meldungsbehandlung von MFC-Code.|  
|**traceMemory**|Nachrichten von MFC Speicher-Management-Code.|  
|**traceCmdRouting**|Nachrichten von MFC Windows-Befehl routing Code.|  
|**traceHtml**|Nachrichten von MFC DHTML-Dialogfeld Unterstützung.|  
|**traceSocket**|Nachrichten von MFC Sockets unterstützt.|  
|**traceOle**|Nachrichten von MFC OLE-Unterstützung.|  
|**traceDatabase**|Nachrichten von MFC Datenbank unterstützt.|  
|**traceInternet**|Nachrichten von MFC Unterstützung.|  
  
 Um eine benutzerdefinierte Kategorie zu deklarieren, deklarieren Sie eine globale Instanz von der `CTraceCategory` wie folgt:  
  
 [!code-cpp[NVC_ATL_Utilities&#109;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]  
  
 Der Kategoriename, `MY_CATEGORY` in diesem Beispiel wird zum Angeben der `category` Parameter. Der erste Parameter ist der Namen der Kategorie, der in den ATL-/MFC-Ablaufverfolgungsprogramm angezeigt werden. Der zweite Parameter ist die standardmäßige Ablaufverfolgungsebene. Dieser Parameter ist optional, und die standardmäßige Ablaufverfolgungsebene ist 0.  
  
 So verwenden Sie eine benutzerdefinierte Kategorie  
  
 [!code-cpp[NVC_ATL_Utilities&#110;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]  
  
 Um anzugeben, dass die Trace-Nachrichten filtern möchten, legen Sie Definitionen für diese Makros in Stdafx.h vor der `#include <atlbase.h>` Anweisung.  
  
 Alternativ können Sie den Filter festlegen, in die Präprozessordirektiven in die **Eigenschaftenseiten** im Dialogfeld. Klicken Sie auf die **Präprozessor** Registerkarte, und legen Sie die globale in der **Präprozessordefinitionen** Bearbeitungsfeld.  
  
 Atlbase.h Standarddefinitionen von der `ATLTRACE2` Makros und diese Definitionen werden verwendet, wenn Sie diese Symbole vor der Verarbeitung atlbase.h definieren.  
  
 In Releasebuilds `ATLTRACE2` kompiliert `(void) 0`.  
  
 `ATLTRACE2`begrenzt den Inhalt der Zeichenfolge, die auf dem Sicherungsmedium nicht mehr als 1023 Zeichen nach der Formatierung gesendet werden.  
  
 **ATLTRACE** und `ATLTRACE2` weisen das gleiche Verhalten, **ATLTRACE** wird aus Gründen der Abwärtskompatibilität.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#111;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [Debuggen und globale Funktionen für die Fehlerberichterstattung](../../atl/reference/debugging-and-error-reporting-global-functions.md)

