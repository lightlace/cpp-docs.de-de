---
title: Klasse CFindReplaceDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
dev_langs:
- C++
helpviewer_keywords:
- text searches, replacing text
- text searches, CFindReplaceDialog class
- Find/Replace dialog box
- replacing text, CFindReplaceDialog class
- CFindReplaceDialog class
- replacing text
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
caps.latest.revision: 25
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
ms.openlocfilehash: 510f6a763dbacb7d4e1b14ea808a4baaaf3d6bf3
ms.lasthandoff: 02/24/2017

---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog-Klasse
Ermöglicht das Suchen/Ersetzen-Dialogfeldern Standardzeichenfolgen in Ihre Anwendung implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Rufen Sie diese Funktion zum Erstellen einer `CFindReplaceDialog` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|Erstellt und zeigt eine `CFindReplaceDialog` im Dialogfeld.|  
|[CFindReplaceDialog::FindNext](#findnext)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das nächste Vorkommen des Suchbegriffs suchen möchte.|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|Rufen Sie diese Funktion zum Abrufen der aktuellen Suchzeichenfolge.|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Rufen Sie diese Funktion zum Abrufen der **FINDREPLACE** Struktur in Ihre registrierten Meldungshandler.|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Rufen Sie diese Funktion zum Abrufen der aktuellen Ersetzungszeichenfolge.|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|Rufen Sie diese Funktion, um zu bestimmen, ob das Dialogfeld beendet wird.|  
|[CFindReplaceDialog::MatchCase](#matchcase)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte die Groß-/Kleinschreibung der Suchzeichenfolge genau übereinstimmen.|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte ganzen Wörtern.|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer alle Vorkommen der Zeichenfolge ersetzt werden soll.|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das aktuelle Wort ersetzt werden soll.|  
|[CFindReplaceDialog::SearchDown](#searchdown)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass die Suche nach unten fortgesetzt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|Eine Struktur, die zur Anpassung einer `CFindReplaceDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den anderen Windows Standarddialogfeldern `CFindReplaceDialog` Objekte sind nicht modal ermöglichen, dass Benutzer mit anderen Fenstern zu interagieren, während Sie sich auf dem Bildschirm. Es gibt zwei Arten von `CFindReplaceDialog` Objekte: suchen, Dialogfelder und Dialogfelder Suchen und ersetzen. Obwohl die Dialogfelder der Benutzer Eingabe-und Zeichenfolgen suchen/ersetzen können, führen sie das Durchsuchen oder Funktionen ersetzen nicht aus. Sie müssen diese in der Anwendung hinzufügen.  
  
 Erstellt ein `CFindReplaceDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor (die keine Argumente verfügt). Da es sich um ein nicht modales Dialogfeld handelt, ordnen Sie das Objekt auf dem Heap mit der **neue** Operator, anstatt auf den Stapel.  
  
 Einmal eine `CFindReplaceDialog` -Objekts, müssen Sie Aufrufen der [erstellen](#create) Member-Funktion erstellen und Anzeigen des Dialogfelds.  
  
 Verwenden der [M_fr](#m_fr) Struktur zum Initialisieren des Dialogfelds vor dem Aufruf von **erstellen**. Die `m_fr` Struktur ist vom Typ [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 In der Reihenfolge für das übergeordnete Fenster Suchen/Ersetzen-Anforderungen benachrichtigt werden sollen, verwenden Sie die Windows [RegisterWindowMessage registriert](http://msdn.microsoft.com/library/windows/desktop/ms644947) funktionieren, und verwenden Sie die [ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d) meldungszuordnung Makro in Ihr Rahmenfenster, die diese registrierte Meldung behandelt.  
  
 Sie können bestimmen, ob der Benutzer dazu entschieden hat, beendet das Dialogfeld mit den `IsTerminating` Member-Funktion.  
  
 `CFindReplaceDialog`Abhängig von der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher enthalten ist.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFindReplaceDialog`, geben Sie eine benutzerdefinierte Vorlage und fügen Sie eine Zuordnung Nachricht, um die Benachrichtigung über die erweiterte Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übergeben werden.  
  
 Es ist nicht erforderlich, die Hookfunktion anpassen.  
  
 Weitere Informationen zur Verwendung von `CFindReplaceDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="a-namecfindreplacedialoga--cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a>CFindReplaceDialog::CFindReplaceDialog  
 Erstellt ein `CFindReplaceDialog`-Objekt.  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>Hinweise  
 Da die `CFindReplaceDialog` -Objekt ist ein nicht modales Dialogfeld, Sie müssen es auf dem Heap erstellen, mit der `new` Operator.  
  
 Während der Zerstörung der Framework wird versucht, führen Sie eine `delete this` auf den Zeiger auf das Dialogfeld. Wenn Sie im Dialogfeld auf den Stapel, erstellt die `this` Zeiger ist nicht vorhanden und kann zu nicht definiertem Verhalten führen.  
  
 Weitere Informationen zu der Konstruktion des `CFindReplaceDialog` von Objekten finden Sie die [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) (Übersicht). Verwenden der [CFindReplaceDialog::Create](#create) Memberfunktion, um das Dialogfeld anzuzeigen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#170;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="a-namecreatea--cfindreplacedialogcreate"></a><a name="create"></a>CFindReplaceDialog::Create  
 Erstellt und zeigt eine Suche oder Suchen/Ersetzen Dialogfeldobjekt abhängig vom Wert `bFindDialogOnly`.  
  
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
 Legen Sie diesen Parameter `TRUE` zum Anzeigen einer **suchen** (Dialogfeld). Legen Sie es auf `FALSE` zum Anzeigen einer **suchen und Ersetzen** Dialogfeld.  
  
 `lpszFindWhat`  
 Ein Zeiger auf die Suchzeichenfolge Standardwert, wenn das Dialogfeld angezeigt wird. Wenn `NULL`, enthält das Dialogfeld die eine Suchzeichenfolge ein Standard nicht.  
  
 `lpszReplaceWith`  
 Ein Zeiger auf die Ersatzzeichenfolge Standardwert, wenn das Dialogfeld angezeigt wird. Wenn `NULL`, enthält das Dialogfeld die Ersatzzeichenfolge Standard nicht.  
  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen im Dialogfeld mit dem bitweisen OR-Operator kombiniert anpassen. Der Standardwert ist `FR_DOWN`, der angibt, dass die Suche nach unten fortgesetzt. Finden Sie unter der [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zu diesen Flags.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld übergeordnete Fenster oder das Besitzer. Dies ist das Fenster, das ist die spezielle Meldung erhalten, dass ein Suchen/Ersetzen-Vorgang angefordert wird. Wenn `NULL`, das Hauptfenster der Anwendung verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeld erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In der Reihenfolge für das übergeordnete Fenster Suchen/Ersetzen-Anforderungen benachrichtigt werden sollen, verwenden Sie die Windows [RegisterWindowMessage registriert](http://msdn.microsoft.com/library/windows/desktop/ms644947) Funktion, deren Rückgabewert einer Meldungsnummer, der für die Anwendung Instanz eindeutig ist. Ihr Rahmenfenster müssen einen Zuordnungseintrag für Nachrichten, die die Callback-Funktion deklariert ( `OnFindReplace` in dem folgenden Beispiel), der diese registrierte Meldung behandelt. Das folgende Codefragment ist ein Beispiel für ein Rahmenfenster (Klasse) mit dem Namen `CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView&#171;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView&#172;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#173;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 Innerhalb der `OnFindReplace` -Funktion interpretiert die Absichten des Benutzers mithilfe der [CFindReplaceDialog::FindNext](#findnext) und [CFindReplaceDialog::IsTerminating](#isterminating) Methoden und Sie den Code für die Suchen/Ersetzen-Vorgänge erstellen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="a-namefindnexta--cfindreplacedialogfindnext"></a><a name="findnext"></a>CFindReplaceDialog::FindNext  
 Mit dieser Funktion wird von Ihrer Callback-Funktion, um festzustellen, ob der Benutzer das nächste Vorkommen der Suchzeichenfolge suchen möchte.  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer das nächste Vorkommen der Suchzeichenfolge suchen möchte; andernfalls 0.  
  
##  <a name="a-namegetfindstringa--cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a>CFindReplaceDialog::GetFindString  
 Mit dieser Funktion wird von Ihrer Callback-Funktion, um die Standardeinstellung, die zu suchende Zeichenfolge abzurufen.  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardeinstellung zu suchende Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="a-namegetnotifiera--cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a>CFindReplaceDialog::GetNotifier  
 Rufen Sie diese Funktion, um einen Zeiger auf das aktuelle Dialogfeld Suchen und Ersetzen abzurufen.  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `lParam`  
 Die **Lparam** Wert übergeben wird, an des Rahmenfensters **OnFindReplace** Member-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktuelle Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Es sollte innerhalb Ihrer Callback-Funktion für den Zugriff auf das aktuelle Dialogfeld seine Memberfunktionen aufrufen, Funktionen und den Zugriff verwendet werden die `m_fr` Struktur.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CFindReplaceDialog::Create](#create) ein Beispiel zum Registrieren der OnFindReplace-Handler zum Empfangen von Benachrichtigungen über das Dialogfeld Suchen und ersetzen.  
  
 [!code-cpp[NVC_MFCDocView&#69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="a-namegetreplacestringa--cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a>CFindReplaceDialog::GetReplaceString  
 Rufen Sie diese Funktion zum Abrufen der aktuellen Ersetzungszeichenfolge.  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardzeichenfolge mit dem gefundene Zeichenfolgen ersetzt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="a-nameisterminatinga--cfindreplacedialogisterminating"></a><a name="isterminating"></a>CFindReplaceDialog::IsTerminating  
 Rufen Sie diese Funktion in Ihrer Callback-Funktion, um festzustellen, ob der Benutzer dazu entschieden hat, um das Dialogfeld zu beenden.  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer dazu entschieden hat, um das Dialogfeld zu beenden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion einen Wert ungleich NULL zurückgibt, sollten Sie Aufrufen der `DestroyWindow` -Memberfunktion des aktuellen Dialogfelds, und alle Dialogfeld Zeigervariable auf **NULL**. Sie können optional auch den zuletzt eingegebenen Suchen/Ersetzen-Text zu speichern und verwenden, um das nächste Suchen/Ersetzen-Dialogfeld zu initialisieren.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="a-namemfra--cfindreplacedialogmfr"></a><a name="m_fr"></a>CFindReplaceDialog::m_fr  
 Zur Anpassung einer `CFindReplaceDialog` Objekt.  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_fr`ist eine Struktur vom Typ [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Membern speichern die Eigenschaften des Objekts im Dialogfeld. Nach dem Erstellen einer `CFindReplaceDialog` -Objekts können Sie `m_fr` verschiedene Werte im Dialogfeld ändern.  
  
 Weitere Informationen zu dieser Struktur finden Sie unter der **FINDREPLACE** -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="a-namematchcasea--cfindreplacedialogmatchcase"></a><a name="matchcase"></a>CFindReplaceDialog::MatchCase  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte die Groß-/Kleinschreibung der Suchzeichenfolge genau übereinstimmen.  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer möchte Vorkommen der Suchzeichenfolge gefunden, die genau die Groß-/Kleinschreibung der Suchzeichenfolge übereinstimmen; andernfalls 0.  
  
##  <a name="a-namematchwholeworda--cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a>CFindReplaceDialog::MatchWholeWord  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte ganzen Wörtern.  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer möchte nur ganze Wörter der Suchzeichenfolge übereinstimmen; andernfalls 0.  
  
##  <a name="a-namereplacealla--cfindreplacedialogreplaceall"></a><a name="replaceall"></a>CFindReplaceDialog::ReplaceAll  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer alle Vorkommen der Zeichenfolge ersetzt werden soll.  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer angefordert hat, dass alle Zeichenfolgen, die übereinstimmende Ersetzungszeichenfolge ersetzt werden; andernfalls 0.  
  
##  <a name="a-namereplacecurrenta--cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a>CFindReplaceDialog::ReplaceCurrent  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das aktuelle Wort ersetzt werden soll.  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer angefordert hat, die derzeit ausgewählte Zeichenfolge mit der Ersetzungszeichenfolge ersetzt werden; andernfalls 0.  
  
##  <a name="a-namesearchdowna--cfindreplacedialogsearchdown"></a><a name="searchdown"></a>CFindReplaceDialog::SearchDown  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer möchte, dass die Suche nach unten fortgesetzt.  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer möchte, dass die Suche nach unten fortgesetzt; 0, wenn der Benutzer die Suche nach oben fortsetzen möchte.  
  
## <a name="see-also"></a>Siehe auch  
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)  

