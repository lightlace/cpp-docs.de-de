---
title: CEditView Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
dev_langs: C++
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 38b8389418657499d43263399f1a05b3a0326c84
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ceditview-class"></a>CEditView-Klasse
Ein Ansichtsklassentyp, die die Funktionalität eines Windows-Bearbeitungssteuerelements bereitstellt und verwendet werden kann, um einfache Textbearbeitungsfunktionalität zu implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CEditView : public CCtrlView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEditView::CEditView](#ceditview)|Konstruiert ein Objekt vom Typ `CEditView`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEditView::FindText](#findtext)|Sucht nach einer Zeichenfolge innerhalb des Texts.|  
|[CEditView::GetBufferLength](#getbufferlength)|Ruft die Länge des der Zeichenpuffer ab.|  
|[CEditView::GetEditCtrl](#geteditctrl)|Ermöglicht den Zugriff auf die `CEdit` Teil einer `CEditView` Objekt (das Windows-Bearbeitungssteuerelements).|  
|[CEditView::GetPrinterFont](#getprinterfont)|Ruft die aktuelle Druckerschriftart ab.|  
|[CEditView::GetSelectedText](#getselectedtext)|Ruft den aktuellen Textauswahl ab.|  
|[CEditView::LockBuffer](#lockbuffer)|Sperrt den Puffer.|  
|[CEditView::PrintInsideRect](#printinsiderect)|Rendert Text in einem bestimmten Rechteck.|  
|[SerializeRaw](#serializeraw)|Serialisiert ein `CEditView` Objekt im unformatierten Text auf den Datenträger.|  
|[CEditView::SetPrinterFont](#setprinterfont)|Legt eine neuen Druckerschriftart fest.|  
|[CEditView::SetTabStops](#settabstops)|Legt Tabstopps für die Bildschirmanzeige und drucken.|  
|[CEditView::UnlockBuffer](#unlockbuffer)|Entsperrt den Puffer.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|Sucht die nächste Vorkommen einer Textzeichenfolge.|  
|[CEditView::OnReplaceAll](#onreplaceall)|Ersetzt alle Vorkommen einer angegebenen Zeichenfolge durch eine neue Zeichenfolge an.|  
|[CEditView::OnReplaceSel](#onreplacesel)|Ersetzt die aktuelle Markierung.|  
|[CEditView::OnTextNotFound](#ontextnotfound)|Wird aufgerufen, wenn ein Suchvorgang findet keine Übereinstimmung einen weiteren beschreibenden Text ein.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|Standardstil für Objekte vom Typ **CEditView.**|  
  
## <a name="remarks"></a>Hinweise  
 Die `CEditView` Klasse bietet die folgenden zusätzlichen Funktionen:  
  
-   Drucken.  
  
-   Suchen und ersetzen.  
  
 Da Klasse `CEditView` ist eine Ableitung von der Klasse `CView`, Objekte der Klasse `CEditView` mit Dokumenten und Dokumentvorlagen verwendet werden können.  
  
 Jede `CEditView` Text des Steuerelements in einem eigenen globalen Arbeitsspeicher-Objekt beibehalten wird. Die Anwendung kann eine beliebige Anzahl von haben `CEditView` Objekte.  
  
 Erstellen von Objekten des Typs `CEditView` Wenn soll ein Bearbeitungsfenster mit den hinzugefügten Funktionen, die oben aufgeführten oder einfachen Text-Editor-Funktionen verwendet werden soll. Ein `CEditView` Objekt einnehmen kann der gesamte Clientbereich eines Fensters. Leiten Sie Ihren eigenen Klassen von `CEditView` hinzufügen oder ändern die grundlegende Funktionen oder Klassen deklarieren, die eine Dokumentvorlage hinzugefügt werden können.  
  
 Die standardmäßige Implementierung der Klasse `CEditView` behandelt die folgenden Befehle: **ID_EDIT_SELECT_ALL**, **ID_EDIT_FIND**, **ID_EDIT_REPLACE**, **ID_EDIT_REPEAT**, und **ID_FILE_PRINT**.  
  
 Das Standardlimit für die Zeichen für `CEditView` ist (1024 \* 1024 1 = 1048575). Dies kann geändert werden, durch Aufrufen der **EM_LIMITTEXT** Funktion der zugrunde liegenden edit-Steuerelement. Allerdings die Grenzwerte unterscheiden sich je nach Betriebssystem und der Typ des Bearbeitungssteuerelements (einzelne oder mehrzeiligen). Weitere Informationen zu dieser Grenzwerte, finden Sie unter [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Zum Ändern dieses Limits in das Steuerelement, überschreiben die `OnCreate()` für funktionsfähig sein, Ihre `CEditView` Klasse, und fügen Sie die folgende Codezeile:  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 Objekte des Typs `CEditView` (oder von abgeleiteten Typen `CEditView`) weisen die folgenden Einschränkungen:  
  
- `CEditView`implementiert nicht "true" Was Sie sehen, ist das Ergebnis (WYSIWYG) bearbeiten. Eine Wahl zwischen Lesbarkeit auf dem Bildschirm und übereinstimmende gedruckte Ausgabe vorliegt `CEditView` "OPTS" Bildschirm Lesbarkeit.  
  
- `CEditView`können Text in nur einer einzigen Schriftart anzeigen. Keine Sonderzeichen Formatierung wird unterstützt. Siehe Klasse [CRichEditView](../../mfc/reference/cricheditview-class.md) für verbesserte Funktionen.  
  
-   Die Größe des Texts einer `CEditView` darf ist beschränkt. Die Beschränkung sind die gleichen wie für die `CEdit` Steuerelement.  
  
 Weitere Informationen zu `CEditView`, finden Sie unter [abgeleitete Sicht Klassen in MFC verfügbare](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="ceditview"></a>CEditView::CEditView  
 Konstruiert ein Objekt vom Typ `CEditView`.  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie die [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) funktionieren, bevor das Bearbeitungssteuerelement verwendet wird. Wenn Sie beim Ableiten einer Klasse von `CEditView` und hinzuzufügen, die Vorlage mit `CWinApp::AddDocTemplate`, das Framework ruft beide dieser Konstruktor und die **erstellen** Funktion.  
  
##  <a name="dwstyledefault"></a>CEditView::dwStyleDefault  
 Enthält den Standardstil der der `CEditView` Objekt.  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses statische Element als übergeben der `dwStyle` Parameter von der **erstellen** -Funktion das Standardformat für Abrufen der `CEditView` Objekt.  
  
##  <a name="findtext"></a>CEditView::FindText  
 Rufen Sie die `FindText` Funktion zum Suchen der `CEditView` Textpuffer des Objekts.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bNext = TRUE,  
    BOOL bCase = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text gefunden werden.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **"true"**, die suchrichtung wird am Ende des Puffers. Wenn **"false"**, die suchrichtung an den Anfang des Puffers ist.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn **"true"**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **"false"**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie der Suchtext ein gefunden wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sucht den Text in den Puffer für den angegebenen Text `lpszFind`, beginnend an der aktuellen Auswahl, in der vom angegebenen Richtung `bNext`, und mit der Groß-/Kleinschreibung von angegebenen `bCase`. Wenn der Text gefunden wird, legt die Auswahl auf den gefundenen Text fest und gibt einen Wert ungleich NULL zurück. Wenn der Text nicht gefunden wird, gibt die Funktion 0 zurück.  
  
 Brauchen Sie normalerweise rufen Sie die `FindText` funktionsfähig, es sei denn, Sie überschreiben `OnFindNext`, welche Aufrufe `FindText`.  
  
##  <a name="getbufferlength"></a>CEditView::GetBufferLength  
 Rufen Sie diese Memberfunktion, um die Anzahl der Zeichen, die derzeit in das Bearbeitungssteuerelement Puffer, nicht einschließlich das null-Abschlusszeichen zu erhalten.  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge in den Puffer.  
  
##  <a name="geteditctrl"></a>CEditView::GetEditCtrl  
 Rufen Sie `GetEditCtrl` zum Abrufen eines Verweises auf das Steuerelement zum Bearbeiten von der Bearbeitungsansicht verwendet.  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein `CEdit`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Steuerelement ist vom Typ [CEdit](../../mfc/reference/cedit-class.md), sodass Sie direkt mit der Windows-Bearbeitungssteuerelements bearbeiten können die `CEdit` Memberfunktionen.  
  
> [!CAUTION]
>  Mithilfe der `CEdit` kann ändern, den Zustand des zugrunde liegenden Windows-Bearbeitungssteuerelements-Objekt. Beispielsweise sollten Sie nicht mithilfe von Einstellungen auf der Registerkarte ändern die [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) ausgeführt, da `CEditView` speichert diese Einstellungen für die Verwendung sowohl in das Steuerelement zum Bearbeiten und drucken. Verwenden Sie stattdessen [CEditView::SetTabStops](#settabstops).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="getprinterfont"></a>CEditView::GetPrinterFont  
 Rufen Sie `GetPrinterFont` um einen Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) Objekt, das die aktuelle Druckerschriftart beschreibt.  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CFont` Objekt, das die aktuelle Druckerschriftart; angibt. **NULL** , wenn die Druckerschriftart nicht festgelegt wurde. Der Zeiger kann temporär sein und sollte nicht für eine spätere Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Druckerschriftart nicht, die Standardeinstellung drucken Verhalten des festgelegt wurde die `CEditView` Klasse mit der Schriftart für die Anzeige gedruckt wird.  
  
 Verwenden Sie diese Funktion, um die aktuelle Druckerschriftart zu bestimmen. Wenn dies nicht der gewünschte Druckerschriftart ist, verwenden [CEditView::SetPrinterFont](#setprinterfont) um ihn zu ändern.  
  
##  <a name="getselectedtext"></a>CEditView::GetSelectedText  
 Rufen Sie `GetSelectedText` So kopieren Sie den markierten Text dann ein `CString` -Objekt, bis zum Ende der Auswahl oder das Zeichen, die vor dem ersten Wagenrücklauf-Zeichen in der Auswahl.  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strResult`  
 Ein Verweis auf die `CString` -Objekt, das den ausgewählten Text zu empfangen.  
  
##  <a name="lockbuffer"></a>CEditView::LockBuffer  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf den Puffer zu erhalten. Der Puffer sollte nicht geändert werden.  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Bearbeitungssteuerelement Puffer.  
  
##  <a name="onfindnext"></a>CEditView::OnFindNext  
 Durchsucht den Text in den Puffer für den angegebenen Text `lpszFind`, in der vom angegebenen Richtung `bNext`, mit der Groß-/Kleinschreibung von angegebenen `bCase`.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text gefunden werden.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **"true"**, die suchrichtung wird am Ende des Puffers. Wenn **"false"**, die suchrichtung an den Anfang des Puffers ist.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn **"true"**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **"false"**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
### <a name="remarks"></a>Hinweise  
 Die Suche beginnt am Anfang der aktuellen Auswahl und erfolgt durch einen Aufruf von [FindText](#findtext). In der Standardimplementierung `OnFindNext` Aufrufe [OnTextNotFound](#ontextnotfound) , wenn der Text nicht gefunden wird.  
  
 Überschreiben Sie `OnFindNext` ändern, wie eine `CEditView`-abgeleitete Objekt sucht nach Text. `CEditView`Aufrufe `OnFindNext` bei Betätigung der Schaltfläche Suchen in der standardmäßigen suchen (Dialogfeld).  
  
##  <a name="onreplaceall"></a>CEditView::OnReplaceAll  
 `CEditView`Aufrufe `OnReplaceAll` Wenn der Benutzer die Schaltfläche "Alle ersetzen" auswählt, in das Standarddialogfeld ersetzen.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text gefunden werden.  
  
 `lpszReplace`  
 Der Text, den der Suchtext ersetzt.  
  
 `bCase`  
 Gibt an, ob die Suche die Groß-/Kleinschreibung beachtet wird. Wenn **"true"**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **"false"**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
### <a name="remarks"></a>Hinweise  
 `OnReplaceAll`durchsucht den Text in den Puffer für den angegebenen Text `lpszFind`, mit der Groß-/Kleinschreibung von angegebenen `bCase`. Die Suche beginnt am Anfang der aktuellen Auswahl. Jedes Mal der Suchtext ein gefunden wird, ersetzt diese Funktion mit den angegebenen Text, Vorkommen des Texts `lpszReplace`. Die Suche erfolgt durch einen Aufruf von [FindText](#findtext). In der Standardimplementierung [OnTextNotFound](#ontextnotfound) wird aufgerufen, wenn der Text nicht gefunden wird.  
  
 Wenn die aktuelle Auswahl nicht übereinstimmt `lpszFind`, die Auswahl wird auf das erste Vorkommen des Texts gemäß aktualisiert `lpszFind` und eine Ersetzung wird nicht ausgeführt. Dies ermöglicht es dem Benutzer zu bestätigen, dass dies Was möchten sie tun, wenn die Auswahl der zu ersetzende Text nicht übereinstimmt.  
  
 Überschreiben Sie `OnReplaceAll` ändern, wie eine `CEditView`-abgeleitete Objekt ersetzt Text.  
  
##  <a name="onreplacesel"></a>CEditView::OnReplaceSel  
 `CEditView`Aufrufe `OnReplaceSel` Wenn der Benutzer die Schaltfläche "ersetzen" auswählt, in das Standarddialogfeld ersetzen.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text gefunden werden.  
  
 `bNext`  
 Gibt die Richtung der Suche. Wenn **"true"**, die suchrichtung wird am Ende des Puffers. Wenn **"false"**, die suchrichtung an den Anfang des Puffers ist.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn **"true"**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **"false"**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
 `lpszReplace`  
 Der Text, den gefundenen Text zu ersetzen.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Ersetzen der Auswahl, durchsucht dieser Funktion den Text in den Puffer für das nächste Vorkommen des Texts gemäß `lpszFind`, in der vom angegebenen Richtung `bNext`, mit der Groß-/Kleinschreibung von angegebenen `bCase`. Die Suche erfolgt durch einen Aufruf von [FindText](#findtext). Wenn der Text nicht gefunden wird, [OnTextNotFound](#ontextnotfound) aufgerufen wird.  
  
 Überschreiben Sie `OnReplaceSel` ändern, wie eine `CEditView`-abgeleitete Objekt ersetzt den markierten Text.  
  
##  <a name="ontextnotfound"></a>CEditView::OnTextNotFound  
 Überschreiben Sie diese Funktion, um die standardmäßige Implementierung zu ändern, der die Windows-Funktion aufruft **MessageBeep**.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text gefunden werden.  
  
##  <a name="printinsiderect"></a>CEditView::PrintInsideRect  
 Rufen Sie `PrintInsideRect` So drucken Sie Text in das Rechteck, angegeben durch *RectLayout*.  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Druckergerätekontext.  
  
 *rectLayout*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT-Struktur](../../mfc/reference/rect-structure1.md) angeben Rechteck, in dem der Text gerendert werden.  
  
 `nIndexStart`  
 Der Index innerhalb des Puffers des ersten Zeichens gerendert werden soll.  
  
 `nIndexStop`  
 Der Index innerhalb des Puffers des Zeichens hinter dem letzten Zeichen gerendert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des nächsten Zeichens gedruckt werden (d. h. das Zeichen nach dem letzten Zeichen dargestellt).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CEditView` Steuerelement verfügt nicht über das Format **ES_AUTOHSCROLL**, Text innerhalb des Rechtecks Rendering umbrochen wird. Wenn das Steuerelement das Format hat **ES_AUTOHSCROLL**, wird der Text am rechten Rand des Rechtecks abgeschnitten.  
  
 Die **rect.bottom** Element von der *RectLayout* Objekts so geändert, dass das Rechteck Dimensionen den Teil des ursprünglichen Rechtecks definieren, die durch den Text belegt wird.  
  
##  <a name="serializeraw"></a>SerializeRaw  
 Rufen Sie `SerializeRaw` haben eine `CArchive` Objekt lesen und Schreiben von Text in die `CEditView` Objekt in eine Textdatei.  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein Verweis auf die `CArchive` -Objekt, das die serialisierten Text gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 `SerializeRaw`unterscheidet sich von `CEditView`die interne Implementierung der `Serialize` liest und schreibt nur den Text ohne Beschreibung des Objekts Daten vor.  
  
##  <a name="setprinterfont"></a>CEditView::SetPrinterFont  
 Rufen Sie `SetPrinterFont` für die Druckerschriftart festzulegen, der vom angegebenen Schriftart `pFont`.  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 Ein Zeiger auf ein Objekt vom Typ `CFont`. Wenn **NULL**, die Schriftart für das Drucken verwendet basiert auf dem Bildschirm-Schriftart.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Ansicht mit immer eine besondere Schriftart für das Drucken verwenden möchten, fügen Sie einen Aufruf `SetPrinterFont` in Ihrer Klasse `OnPreparePrinting` Funktion. Diese virtuelle Funktion wird aufgerufen, vor dem Drucken tritt auf, damit die Änderung der Schriftart stattfindet, bevor Sie den Inhalt der Ansicht gedruckt werden.  
  
##  <a name="settabstops"></a>CEditView::SetTabStops  
 Mit dieser Funktion wird zum Festlegen von Tabstopps, die zum Anzeigen und drucken.  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>Parameter  
 `nTabStops`  
 Breite des Tabstopp in Dialogeinheiten.  
  
### <a name="remarks"></a>Hinweise  
 Nur eine einzelne Tabstopp Breite wird unterstützt. ( `CEdit` Objekte unterstützen mehrere Tabulatorposition.) Breiten befinden sich in Dialogeinheiten, die ein Viertel der durchschnittliche Zeichenbreite (basierend auf Groß- und Kleinschreibung nur alphabetische Zeichen) der Schriftart, die zum Zeitpunkt der drucken oder die Anzeige von gleich. Verwenden Sie nicht `CEdit::SetTabStops` da `CEditView` muss den Wert Tabstopp Zwischenspeichern.  
  
 Diese Funktion ändert nur die Registerkarten des Objekts, für die sie aufgerufen wird. So ändern Sie die Registerkarte "beendet werden soll, für die einzelnen `CEditView` Objekt in der Anwendung, rufen Sie jedes Objekt `SetTabStops` Funktion.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment legt Tabstopps im Steuerelement, um jede vierte Zeichen durch das Messen sorgfältig der Schriftart, die das Steuerelement verwendet.  
  
 [!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="unlockbuffer"></a>CEditView::UnlockBuffer  
 Rufen Sie diese Memberfunktion um den Puffer zu entsperren.  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `UnlockBuffer` Sie nach dem unter Verwendung des Zeigers zurückgegebenes [LockBuffer](#lockbuffer).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel SUPERPAD](../../visual-cpp-samples.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
