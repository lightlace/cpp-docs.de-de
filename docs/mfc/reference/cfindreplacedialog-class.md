---
title: CFindReplaceDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
dev_langs:
- C++
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21499f65ac762dfd08d90decad41eedf3dfc5cdf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368981"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog-Klasse
Ermöglicht die Standardzeichenfolge in Dateien suchen/ersetzen-Dialogfelder in der Anwendung zu implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Mit dieser Funktion wird zum Erstellen einer `CFindReplaceDialog` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|Erstellt und zeigt eine `CFindReplaceDialog` (Dialogfeld).|  
|[CFindReplaceDialog::FindNext](#findnext)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte das nächste Vorkommen der Suchzeichenfolge suchen.|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|Mit dieser Funktion wird zum Abrufen der aktuellen Suchzeichenfolge.|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Mit dieser Funktion wird zum Abrufen der **FINDREPLACE** Struktur Ihrer registrierten Nachrichtenhandler.|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Mit dieser Funktion wird zum Abrufen der aktuellen Ersetzungszeichenfolge.|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|Rufen Sie diese Funktion, um zu bestimmen, ob das Dialogfeld beendet wird.|  
|[CFindReplaceDialog::MatchCase](#matchcase)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte die Groß-/Kleinschreibung Find angegebene Zeichenfolge genau übereinstimmen.|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte nach ganzen Wörtern an.|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass alle Vorkommen der Zeichenfolge ausgetauscht werden.|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass das aktuelle Wort ersetzt werden.|  
|[CFindReplaceDialog::SearchDown](#searchdown)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass die Suche nach unten zu fortfahren.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|Eine Struktur, die zum Anpassen einer `CFindReplaceDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den anderen Windows allgemeine Dialogfelder `CFindReplaceDialog` Objekte sind nicht modalen, sodass Benutzer für die Interaktion mit anderen Fenstern, während sie auf dem Bildschirm sind. Es gibt zwei Arten von `CFindReplaceDialog` Objekte: Suchen der Dialogfelder und Dialogfelder in Dateien suchen/ersetzen. Obwohl die Dialogfelder den Benutzer Eingabe suchen und Suchen/Ersetzen von Zeichenfolgen zuzulassen, führen sie das Durchsuchen oder zum Ersetzen der Funktionen nicht aus. Sie müssen diese an die Anwendung hinzufügen.  
  
 So erstellen Sie eine `CFindReplaceDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor (die keine Argumente besitzt). Da es sich um ein nicht modales Dialogfeld handelt, reservieren Sie das Objekt auf dem Heap mit dem **neue** -Operator, anstatt auf dem Stapel.  
  
 Einmal eine `CFindReplaceDialog` -Objekts, rufen Sie die [erstellen](#create) Memberfunktion zum Erstellen und Anzeigen des Dialogfelds "".  
  
 Verwenden der [M_fr](#m_fr) Struktur initialisieren Sie das Dialogfeld vor dem Aufruf **erstellen**. Die `m_fr` Struktur ist vom Typ [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.  
  
 In der Reihenfolge für das übergeordnete Fenster in Dateien suchen/ersetzen-Anforderungen benachrichtigt zu werden, verwenden Sie die Windows [RegisterWindowMessage registriert](http://msdn.microsoft.com/library/windows/desktop/ms644947) Funktion, und verwenden Sie die [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message) meldungszuordnung Makro in Ihrem Rahmen Fenster, in dem diese registrierte Meldung verarbeitet.  
  
 Sie können bestimmen, ob der Benutzer dazu entschieden hat, beenden Sie das Dialogfeld mit den `IsTerminating` Memberfunktion.  
  
 `CFindReplaceDialog` basiert auf der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher ausgeliefert wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFindReplaceDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten mit der Basisklasse übergeben werden.  
  
 Anpassen von die Hookfunktion ist nicht erforderlich.  
  
 Weitere Informationen zur Verwendung von `CFindReplaceDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog  
 Erstellt ein `CFindReplaceDialog`-Objekt.  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>Hinweise  
 Da die `CFindReplaceDialog` Objekt ist ein nicht modales Dialogfeld, Sie müssen es auf dem Heap erstellen, mit der `new` Operator.  
  
 Während der Zerstörung, versucht das Framework zum Ausführen einer `delete this` auf den Zeiger auf das Dialogfeld. Wenn Sie im Dialogfeld auf den Stapel, erstellt der `this` Zeiger ist nicht vorhanden und kann zu nicht definiertem Verhalten führen.  
  
 Weitere Informationen zu der Konstruktion des `CFindReplaceDialog` anzuzeigen, die [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) (Übersicht). Verwenden der [CFindReplaceDialog::Create](#create) Member-Funktion, um das Dialogfeld anzuzeigen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="create"></a>  CFindReplaceDialog::Create  
 Erstellt und zeigt suchen oder in Dateien suchen/ersetzen Dialogfeldobjekt, abhängig vom Wert des `bFindDialogOnly`.  
  
```  
virtual BOOL Create(
    BOOL bFindDialogOnly,  
    LPCTSTR lpszFindWhat,  
    LPCTSTR lpszReplaceWith = NULL,  
    DWORD dwFlags = FR_DOWN,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bFindDialogOnly`  
 Legen Sie diesen Parameter auf `TRUE` zum Anzeigen einer **suchen** (Dialogfeld). Legen Sie es auf `FALSE` zum Anzeigen einer **in Dateien suchen/ersetzen** (Dialogfeld).  
  
 `lpszFindWhat`  
 Ein Zeiger auf die Suchzeichenfolge Standardeinstellung, wenn das Dialogfeld angezeigt wird. Wenn `NULL`, des Dialogfelds "" enthält keine Standardwert zu suchende Zeichenfolge.  
  
 `lpszReplaceWith`  
 Ein Zeiger auf die Ersatzzeichenfolge Standardeinstellung, wenn das Dialogfeld angezeigt wird. Wenn `NULL`, des Dialogfelds "" enthält keine Standard-Ersetzungszeichenfolge.  
  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, zum Anpassen der Einstellungen im Dialogfeld mit dem bitweisen OR-Operator kombiniert. Der Standardwert ist `FR_DOWN`, was bedeutet, dass wird bei der Suche nach unten zu fortfahren. Finden Sie unter der [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835) Struktur in das Windows SDK für Weitere Informationen zu diesen Flags.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld über- oder Besitzer Fenster. Dies ist das Fenster, das erhält die Sondermeldung gibt an, dass eine Aktion in Dateien suchen/ersetzen angefordert wird. Wenn `NULL`, das Hauptfenster der Anwendung verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeld erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Reihenfolge für das übergeordnete Fenster in Dateien suchen/ersetzen-Anforderungen benachrichtigt zu werden, verwenden Sie die Windows [RegisterWindowMessage registriert](http://msdn.microsoft.com/library/windows/desktop/ms644947) Funktion, deren Rückgabewert eine eindeutige Instanz der Anwendung Meldungsnummer ist. Die Frame-Fensters müssen einen Nachrichtenzuordnungseintrag, die die Rückruffunktion deklariert ( `OnFindReplace` in das folgende Beispiel), die diese registrierte Meldung verarbeitet. Das folgende Codefragment ist ein Beispiel für eine Rahmenfenster (Klasse) mit dem Namen hierzu `CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 Innerhalb der `OnFindReplace` -Funktion interpretiert werden, den Zweck des Benutzers mithilfe der [CFindReplaceDialog::FindNext](#findnext) und [CFindReplaceDialog::IsTerminating](#isterminating) Methoden und Sie den Code zu erstellen für die Suchen/Ersetzen-Vorgänge.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="findnext"></a>  CFindReplaceDialog::FindNext  
 Mit dieser Funktion wird von Ihrer Callback-Funktion, um festzustellen, ob der Benutzer möchte das nächste Vorkommen der Suchzeichenfolge suchen.  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer möchte das nächste Vorkommen der Suchzeichenfolge suchen; andernfalls 0.  
  
##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString  
 Mit dieser Funktion wird von Ihrer Callback-Funktion, um die Standardeinstellung, die zu suchende Zeichenfolge abzurufen.  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardeinstellung zu suchende Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier  
 Rufen Sie diese Funktion, um einen Zeiger auf das aktuelle Dialogfeld Suchen und Ersetzen abzurufen.  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `lParam`  
 Die **Lparam** an des Rahmenfensters übergebene Wert **OnFindReplace** Memberfunktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktuelle Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Er sollte innerhalb der Rückruffunktion für den Zugriff auf das aktuelle Dialogfeld Aufrufen seiner Member, Funktionen und den Zugriff verwendet werden die `m_fr` Struktur.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CFindReplaceDialog::Create](#create) ein Beispiel zum Empfang von Benachrichtigungen über das Dialogfeld Suchen und Ersetzen OnFindReplace Handler registriert werden soll.  
  
 [!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString  
 Mit dieser Funktion wird zum Abrufen der aktuellen Ersetzungszeichenfolge.  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardzeichenfolge, durch die gefundene Zeichenfolgen ersetzt werden soll.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating  
 Mit dieser Funktion wird in Ihrer Callback-Funktion, um zu bestimmen, ob der Benutzer dazu entschieden hat, um das Dialogfeld zu beenden.  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer dazu entschieden hat, um das Dialogfeld zu beenden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion ungleich NULL zurückgibt, sollten Sie Aufrufen der `DestroyWindow` Memberfunktion des aktuellen Dialogfelds und alle Dialogfeld Zeigervariablen, **NULL**. Sie können optional auch die zuletzt eingegebenen in Dateien suchen/ersetzen-Text speichern und verwenden, um das nächste in Dateien suchen/ersetzen-Dialogfeld zu initialisieren.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr  
 Zum Anpassen einer `CFindReplaceDialog` Objekt.  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_fr` ist eine Struktur vom Typ [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Membern speichern Sie die Eigenschaften des Objekts im Dialogfeld. Nach dem Erstellen einer `CFindReplaceDialog` -Objekt können Sie `m_fr` Sie verschiedene Werte im Dialogfeld ändern.  
  
 Weitere Informationen zu dieser Struktur finden Sie unter der **FINDREPLACE** Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte die Groß-/Kleinschreibung Find angegebene Zeichenfolge genau übereinstimmen.  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer möchte Vorkommen der Suchzeichenfolge zu suchen, die genau die Groß-/Kleinschreibung der Suchzeichenfolge übereinstimmen; andernfalls 0.  
  
##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte nach ganzen Wörtern an.  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer möchte nur die Wörter der Suchzeichenfolge übereinstimmen; andernfalls 0.  
  
##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass alle Vorkommen der Zeichenfolge ausgetauscht werden.  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer angefordert hat, dass alle Zeichenfolgen, die übereinstimmende Ersetzungszeichenfolge ersetzt werden; andernfalls 0.  
  
##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass das aktuelle Wort ersetzt werden.  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer angefordert hat, dass die aktuell ausgewählte Zeichenfolge durch die Ersetzungszeichenfolge ersetzt werden; andernfalls 0.  
  
##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass die Suche nach unten zu fortfahren.  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer die Suche nach unten zu fortfahren möchte; 0, wenn der Benutzer möchte, dass die Suche nach oben zu fortfahren.  
  
## <a name="see-also"></a>Siehe auch  
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)  
