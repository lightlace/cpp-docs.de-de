---
title: CString-Formatierung und Meldungsfeldanzeige | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 125d0d3ec1549b9eba46cbfebfb7ecfe2c2186d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387178"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString-Formatierung und Meldungsfeldanzeige

Eine Reihe von Funktionen werden bereitgestellt, um zu formatieren und Analysieren von `CString` Objekte. Sie können diese Funktionen verwenden, immer dann, wenn Sie zum Bearbeiten von `CString` Objekte, aber sie sind besonders nützlich, für die Formatierung von Zeichenfolgen, die in der MessageBox-Text angezeigt werden.

Diese Gruppe von Funktionen enthält auch eine globale Routine für die ein Meldungsfeld angezeigt.

### <a name="cstring-functions"></a>CString-Funktionen

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|Extrahiert die Teilzeichenfolgen, getrennt durch ein einzelnes Zeichen aus einer angegebenen Quellzeichenfolge.|
|[AfxFormatString1](#afxformatstring1)|Ersetzt eine angegebene Zeichenfolge für die Formatierungszeichen "%1" in einer Zeichenfolge in der Zeichenfolgentabelle enthalten.|
|[AfxFormatString2](#afxformatstring2)|Ersetzung von zwei Zeichenfolgen für das Format Zeichen "%1" und "%2" in einer Zeichenfolge in der Tabelle enthalten sind.|
|[AfxMessageBox](#afxmessagebox)|Zeigt ein Meldungsfenster an.|

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxextractsubstring"></a>  AfxExtractSubString

Diese globale Funktion kann verwendet werden, um eine Unterzeichenfolge aus einer angegebenen Quellzeichenfolge zu extrahieren.

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>Parameter

*rString*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/using-cstring.md) -Objekt, das eine einzelne Teilzeichenfolge erhält.

*lpszFullString*<br/>
Zeichenfolge, die den vollständigen Text der Zeichenfolge, die aus zu extrahieren.

*iSubString*<br/>
Nullbasierte Index, der die Teilzeichenfolge extrahiert aus *LpszFullString*.

*chSep*<br/>
Trennzeichen zum Trennen von untergeordneten Zeichenfolgen verwendet.

### <a name="return-value"></a>Rückgabewert

True, wenn die Funktion erfolgreich die Teilzeichenfolge am angegebenen Index extrahiert. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Funktion ist nützlich für das Extrahieren von mehreren Teilzeichenfolgen aus einer Quellzeichenfolge, wenn ein bekanntes einzelnes Zeichen jede untergeordnete Zeichenfolge trennt. Diese Funktion sucht, ab dem Anfang der *LpszFullString* Parameter bei jedem Aufruf.

Diese Funktion gibt "false" zurück, wenn entweder *LpszFullString* auf NULL festgelegt ist oder die Funktion Erreichen des Endes des *LpszFullString* ohne suchen *iSubString*+ 1 Vorkommen des angegebenen Trennzeichens. Die *rString* Parameter wird von den ursprünglichen Wert nicht geändert werden, wenn *LpszFullString* wurde auf NULL festgelegt; andernfalls der *rString* -Parameter eine leere Zeichenfolge festgelegt wird, wenn die Teilzeichenfolge konnte nicht extrahiert werden, für den angegebenen Index.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxformatstring1"></a>  AfxFormatString1

Ersetzt die Zeichenfolge verweist *lpsz1* für alle Instanzen der Zeichen "%1" in der Zeichenfolge identifizierte Ressource *nIDS*.

```
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>Parameter

*rString*<br/>
Ein Verweis auf eine `CString` -Objekt, das die resultierende Zeichenfolge enthalten soll, nachdem die Ersetzung ausgeführt wird.

*nIDS*<br/>
Die Ressourcen-ID der Vorlagenzeichenfolge, die auf dem die Ersetzung ausgeführt wird.

*lpsz1*<br/>
Eine Zeichenfolge, die das Format ersetzt werden Zeichen "%1" in der Vorlagenzeichenfolge.

### <a name="remarks"></a>Hinweise

Die neu gebildete Zeichenfolge befindet sich in *rString*. Wenn die Zeichenfolge in der Zeichenfolgentabelle "Datei %1 wurde nicht gefunden" wird z. B. und *lpsz1* ist gleich "C:\MYFILE. TXT", klicken Sie dann *rString* enthält die Zeichenfolge"C:\MYFILE-Datei. TXT wurde nicht gefunden". Diese Funktion ist nützlich für das Formatieren von Zeichenfolgen, die an die Meldungsfelder und andere Fenster gesendet.

Wenn die Formatierungszeichen "%1" mehr als einmal in der Zeichenfolge angezeigt, werden mehrere Ersetzungen gestellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxformatstring2"></a>  AfxFormatString2

Ersetzt die Zeichenfolge verweist *lpsz1* für alle Instanzen von den Zeichen "%1", und die Zeichenfolge, die auf zeigt *lpsz2* für alle Instanzen der Zeichen "%2", in der Zeichenfolge-Ressource identifizierte *nIDS*.

```
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>Parameter

*rString*<br/>
Ein Verweis auf die `CString` , wird die resultierende Zeichenfolge enthalten, nachdem die Ersetzung ausgeführt wird.

*nIDS*<br/>
Die Zeichenfolgen-ID der Tabelle der Vorlagenzeichenfolge, die auf dem die Ersetzung ausgeführt wird.

*lpsz1*<br/>
Eine Zeichenfolge, die das Format ersetzt werden Zeichen "%1" in der Vorlagenzeichenfolge.

*lpsz2*<br/>
Eine Zeichenfolge, die das Format ersetzt werden Zeichen "%2" in der Vorlagenzeichenfolge.

### <a name="remarks"></a>Hinweise

Die neu gebildete Zeichenfolge befindet sich in *rString*. Wenn die Zeichenfolge in der Zeichenfolgentabelle "Datei %1 nicht gefunden im Verzeichnis %2" ist z. B. *lpsz1* verweist auf "MYFILE. "TXT", und *lpsz2* verweist Sie auf "C:\MYDIR", klicken Sie dann *rString* enthält die Zeichenfolge "MYFILE-Datei. TXT im Verzeichnis C:\MYDIR nicht gefunden."

Wenn das Format Zeichen "%1" oder "%2" mehr als einmal in der Zeichenfolge angezeigt wird, werden mehrere Ersetzungen vorgenommen werden. Sie müssen nicht in numerischer Reihenfolge angegeben werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxmessagebox"></a>  AfxMessageBox

Zeigt ein Meldungsfeld auf dem Bildschirm an.

```
int AfxMessageBox(
    LPCTSTR lpszText,
    UINT nType = MB_OK,
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,
    UINT nType = MB_OK,
    UINT nIDHelp = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Zeigt auf ein `CString`-Objekt oder auf eine auf NULL endende Zeichenfolge, worin die im Meldungsfeld anzuzeigende Meldung enthalten ist.

*nType*<br/>
Der Stil des Meldungsfelds. Wenden Sie eines der [meldungsfeldstile](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) in das Feld.

*nIDHelp*<br/>
Die Hilfekontext-ID für die Meldung; 0 gibt an, dass der Standardhilfekontext der Anwendung verwendet wird.

*nIDPrompt*<br/>
Eine eindeutige ID, die verwendet wird, um auf eine Zeichenfolge in der Zeichenfolgentabelle zu verweisen.

### <a name="return-value"></a>Rückgabewert

Null (0), wenn nicht genügend Arbeitsspeicher vorhanden ist, um des Meldungsfelds anzuzeigen; andernfalls wird einer der folgenden Werte zurückgegeben:

- IDABORT die Abbrechen-Schaltfläche wurde ausgewählt.

- IDCANCEL die Abbrechen-Schaltfläche wurde ausgewählt.

- Schaltfläche "IDIGNORE der ignorieren" wurde ausgewählt.

- Schaltfläche "IDNO der Nein" ausgewählt wurde.

- IDOK die OK-Schaltfläche wurde ausgewählt.

- Schaltfläche "IDRETRY die Wiederholen" wurde ausgewählt.

- Schaltfläche "Ja die IDYES" ausgewählt wurde.

Wenn ein Meldungsfeld die Schaltfläche "Abbrechen" verfügt, wird der IDCANCEL-Wert zurückgegeben werden, wenn entweder die ESC-Taste gedrückt wird oder die Schaltfläche "Abbrechen" aktiviert ist. Enthält das Meldungsfeld keine Schaltfläche "Abbrechen", hat das Drücken der ESC-TASTE keine Auswirkung.

Die Funktionen [AfxFormatString1](#afxformatstring1) und [AfxFormatString2](#afxformatstring2) Formatieren von Text, der in einem Meldungsfeld angezeigt wird nützlich sein können.

### <a name="remarks"></a>Hinweise

Die erste Form dieser überladenen Funktion angezeigt, die eine Textzeichenfolge verweist *LpszText* in der MessageBox und verwendet *nIDHelp* um einen Hilfekontext zu beschreiben. Der Hilfekontext wird verwendet, um zu einem zugeordneten Hilfethema zu wechseln, wenn der Benutzer die Hilfetaste drückt (in der Regel F1).

Die zweite Form der Funktion verwendet die Zeichenfolgenressource mit der ID *nIDPrompt* eine Meldung im Meldungsfeld angezeigt. Die zugeordnete Hilfeseite wird durch den Wert gefunden *nIDHelp*. Wenn der Wert von *nIDHelp* verwendet (1), wird die Zeichenfolgenressource-ID, *nIDPrompt*, wird für den Hilfekontext verwendet. Weitere Informationen zum Definieren eines Hilfekontexts finden Sie unter [technischer Hinweis 28](../../mfc/tn028-context-sensitive-help-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)
