---
title: CString-Formatierung und Meldungsfeldanzeige | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects, formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
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
ms.sourcegitcommit: 3d045736f9a54d344c67e3f7408198e65a0bc95f
ms.openlocfilehash: 356562dc61971aa7a74ce9e9be94fc34af58f6f9
ms.lasthandoff: 03/29/2017

---
# <a name="cstring-formatting-and-message-box-display"></a>CString-Formatierung und Meldungsfeldanzeige
Eine Reihe von Funktionen werden bereitgestellt, um formatieren und Analysieren von `CString` Objekte. Wenn Sie bearbeiten müssen, verwenden Sie diese Funktionen können `CString` Objekte, aber sie sind besonders nützlich für das Formatieren von Zeichenfolgen, die in der MessageBox-Text angezeigt werden.  
  
 Diese Gruppe von Funktionen enthält auch eine globale Routine für ein Meldungsfeld angezeigt.  
  
### <a name="cstring-functions"></a>CString-Funktionen  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|Extrahiert Teilzeichenfolgen, getrennt durch ein einzelnes Zeichen aus einer angegebenen Quellzeichenfolge.|  
|[AfxFormatString1](#afxformatstring1)|Ersetzt eine angegebene Zeichenfolge für die Formatierungszeichen "%1" in eine Zeichenfolge in der Zeichenfolgentabelle enthalten.|  
|[AfxFormatString2](#afxformatstring2)|Ersetzt durch zwei Zeichenfolgen für das Format Zeichen "%1" und "%2" in einer Zeichenfolge in der Zeichenfolgentabelle enthalten sind.|  
|[AfxMessageBox](#afxmessagebox)|Zeigt ein Meldungsfenster an.|  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxextractsubstring"></a>AfxExtractSubString  
 Dieser globale Funktion kann verwendet werden, um eine Unterzeichenfolge aus einer bestimmten Quellzeichenfolge zu extrahieren.  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>Parameter  
 *rString*  
 -   Ein Verweis auf eine [CString](../../atl-mfc-shared/using-cstring.md) -Objekt, das eine einzelne Teilzeichenfolge erhält.  
  
 *lpszFullString*  
 -   Zeichenfolge, enthält den vollständigen Text der Zeichenfolge, die aus zu extrahieren.  
  
 *iSubString*  
 -   Nullbasierte Index der Teilzeichenfolge extrahiert aus *LpszFullString*.  
  
 *chSep*  
 -   Trennzeichen zum Trennen der Teilzeichenfolgen.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn die Funktion erfolgreich mit die Teilzeichenfolge am angegebenen Index extrahiert, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich für das Extrahieren von mehreren Teilzeichenfolgen aus einer Quellzeichenfolge, wenn ein bekanntes einzelnes Zeichen jede Teilzeichenfolge trennt. Diese Funktion sucht vom Anfang der `lpszFullString` Parameter jedes Mal aufgerufen wird.  
  
 Diese Funktion gibt "false" zurück, wenn entweder `lpszFullString` festgelegt ist, um **NULL** oder die Funktion Erreichen des Endes des `lpszFullString` ohne suchen `iSubString`+ 1 Vorkommen des angegebenen Trennzeichens. Die `rString` Parameter wird nicht aus den ursprünglichen Wert geändert werden, wenn `lpszFullString` wurde **NULL**ist, andernfalls der `rString` Parameter auf die leere Zeichenfolge festgelegt ist, wenn die Teilzeichenfolge für den angegebenen Index nicht ermittelt werden konnte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxformatstring1"></a>AfxFormatString1  
 Ersetzt die Zeichenfolge, die durch `lpsz1` für alle Instanzen der Zeichen "%1" in der Vorlage eine Zeichenfolgenressource identifizierten `nIDS`.  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>Parameter  
 `rString`  
 Ein Verweis auf eine `CString` -Objekt, das die resultierende Zeichenfolge enthalten soll, nachdem die Ersetzung ausgeführt wird.  
  
 `nIDS`  
 Die Ressourcen-ID der Vorlagenzeichenfolge, die auf dem die Ersetzung ausgeführt wird.  
  
 `lpsz1`  
 Eine Zeichenfolge, die das Format Ersetzen Zeichen "%1" in der Vorlagenzeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Das neu formatierte Zeichenfolge befindet sich in `rString`. Die Zeichenfolge in der Zeichenfolgentabelle beispielsweise "Datei" % 1"wurde nicht gefunden", und `lpsz1` ist gleich "C:\MYFILE. TXT", klicken Sie dann `rString` die Zeichenfolge"File C:\MYFILE. TXT nicht gefunden". Diese Funktion ist nützlich für das Formatieren von Zeichenfolgen, die auf MessageBoxes und anderen Fenstern gesendet.  
  
 Wenn die Formatierungszeichen "%1" mehr als einmal in der Zeichenfolge angezeigt, werden mehrere substitutionen vorgenommen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxformatstring2"></a>AfxFormatString2  
 Ersetzt die Zeichenfolge, die durch `lpsz1` für alle Instanzen der Zeichen "%1" und die Zeichenfolge, die durch `lpsz2` für alle Instanzen der Zeichen "%2", in der Vorlage eine Zeichenfolgenressource identifizierten `nIDS`.  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>Parameter  
 `rString`  
 Ein Verweis auf die `CString` , wird die resultierende Zeichenfolge enthalten, nachdem die Ersetzung ausgeführt wird.  
  
 `nIDS`  
 Die Zeichenfolgen-ID der Tabelle der Vorlagenzeichenfolge, die auf dem die Ersetzung ausgeführt wird.  
  
 `lpsz1`  
 Eine Zeichenfolge, die das Format Ersetzen Zeichen "%1" in der Vorlagenzeichenfolge.  
  
 `lpsz2`  
 Eine Zeichenfolge, die das Format Ersetzen Zeichen "%2" in der Vorlagenzeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Das neu formatierte Zeichenfolge befindet sich in `rString`. Wenn die Zeichenfolge in der Zeichenfolgentabelle "Datei" % 1"nicht gefunden wird, im Verzeichnis %2" ist beispielsweise `lpsz1` verweist auf "Datei. TXT", und `lpsz2` verweist auf"C:\MYDIR", klicken Sie dann `rString` die Zeichenfolge"File-Datei. TXT im Verzeichnis C:\MYDIR nicht gefunden"  
  
 Wenn das Format Zeichen "%1" oder "%2" mehr als einmal in der Zeichenfolge angezeigt wird, werden mehrere substitutionen vorgenommen werden. Sie müssen nicht in numerischer Reihenfolge befinden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities #26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxmessagebox"></a>AfxMessageBox  
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
 `lpszText`  
 Zeigt auf ein `CString`-Objekt oder auf eine auf NULL endende Zeichenfolge, worin die im Meldungsfeld anzuzeigende Meldung enthalten ist.  
  
 `nType`  
 Der Stil des Meldungsfelds. Wendet keine der der [meldungsfeldstile](../../mfc/reference/message-box-styles.md) in das Feld.  
  
 `nIDHelp`  
 Die Hilfekontext-ID für die Meldung; 0 gibt an, dass der Standardhilfekontext der Anwendung verwendet wird.  
  
 `nIDPrompt`  
 Eine eindeutige ID, die verwendet wird, um auf eine Zeichenfolge in der Zeichenfolgentabelle zu verweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Null (0), wenn nicht genügend Arbeitsspeicher vorhanden ist, um des Meldungsfelds anzuzeigen; andernfalls wird einer der folgenden Werte zurückgegeben:  
  
- **IDABORT** der Schaltfläche ausgewählt wurde.  
  
- **IDCANCEL** Schaltfläche die "Abbrechen" ausgewählt wurde.  
  
- **IDIGNORE** Schaltfläche "der ignorieren" wurde ausgewählt.  
  
- **IDNO** der keine Schaltfläche "ausgewählt wurde.  
  
- **IDOK** die OK-Schaltfläche aktiviert wurde.  
  
- **IDRETRY** der Wiederholen-Schaltfläche ausgewählt wurde.  
  
- **IDYES** Ja der Schaltfläche "ausgewählt wurde.  
  
 Wenn ein Meldungsfeld eine Schaltfläche "Abbrechen", hat die **IDCANCEL** Wert wird zurückgegeben, wenn die ESC-Taste gedrückt wird, oder die Schaltfläche "Abbrechen" aktiviert ist. Enthält das Meldungsfeld keine Schaltfläche "Abbrechen", hat das Drücken der ESC-TASTE keine Auswirkung.  
  
 Die Funktionen [AfxFormatString1](#afxformatstring1) und [AfxFormatString2](#afxformatstring2) kann hilfreich bei der Formatierung von Text, der in einem Meldungsfeld angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Mit der ersten Form dieser überladenen Funktion wird eine Textzeichenfolge angezeigt, auf die durch `lpszText` im Meldungsfeld verwiesen wird, und diese Form verwendet `nIDHelp`, um einen Hilfekontext zu beschreiben. Der Hilfekontext wird verwendet, um zu einem zugeordneten Hilfethema zu wechseln, wenn der Benutzer die Hilfetaste drückt (in der Regel F1).  
  
 Das zweite Form der Funktion verwendet die Zeichenfolgenressource mit der ID `nIDPrompt`, um eine Meldung im Meldungsfeld anzuzeigen. Die zugeordnete Hilfeseite wird über den Wert von `nIDHelp` gefunden. Wenn der Wert von `nIDHelp` verwendet (1), wird die Zeichenfolgenressource-ID, `nIDPrompt`, wird für den Hilfekontext verwendet. Weitere Informationen zum Definieren eines Hilfekontexts finden Sie unter [technischer Hinweis 28](../../mfc/tn028-context-sensitive-help-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md)

