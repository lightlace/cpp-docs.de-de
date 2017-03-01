---
title: CEditView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEditView
dev_langs:
- C++
helpviewer_keywords:
- text editors, CEditView class
- text editors
- edit controls, classes
- views, classes
- CEditView class
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
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
ms.openlocfilehash: 688a6c0e871a9456b85a8ed02ce43d7fa9ca8180
ms.lasthandoff: 02/24/2017

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
|[CEditView::GetBufferLength](#getbufferlength)|Ruft die Länge des Zeichenpuffers.|  
|[CEditView::GetEditCtrl](#geteditctrl)|Ermöglicht den Zugriff auf die `CEdit` Teil einer `CEditView` Objekt (Windows-Bearbeitungssteuerelements).|  
|[CEditView::GetPrinterFont](#getprinterfont)|Ruft die aktuelle Druckerschriftart ab.|  
|[CEditView::GetSelectedText](#getselectedtext)|Ruft die aktuelle Textauswahl ab.|  
|[CEditView::LockBuffer](#lockbuffer)|Sperrt den Puffer.|  
|[CEditView::PrintInsideRect](#printinsiderect)|Rendert Text in einem bestimmten Rechteck.|  
|[SerializeRaw](#serializeraw)|Serialisiert ein `CEditView` Objekt auf dem Datenträger als unformatierten Text.|  
|[CEditView::SetPrinterFont](#setprinterfont)|Legt eine neuen Druckerschriftart fest.|  
|[CEditView::SetTabStops](#settabstops)|Legt Tabstopps für die Bildschirmanzeige und drucken.|  
|[CEditView::UnlockBuffer](#unlockbuffer)|Hebt die Sperre des Puffers.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|Sucht die nächste Vorkommen einer Textzeichenfolge zurück.|  
|[CEditView::OnReplaceAll](#onreplaceall)|Ersetzt alle Vorkommen einer angegebenen Zeichenfolge durch eine neue Zeichenfolge an.|  
|[CEditView::OnReplaceSel](#onreplacesel)|Ersetzt die aktuelle Auswahl.|  
|[CEditView::OnTextNotFound](#ontextnotfound)|Wird aufgerufen, wenn ein Suchvorgang keine weiteren Text entsprechen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|Standardstil für Objekte vom Typ **CEditView.**|  
  
## <a name="remarks"></a>Hinweise  
 Die `CEditView` -Klasse bietet die folgenden zusätzlichen Funktionen:  
  
-   Drucken.  
  
-   Suchen und ersetzen.  
  
 Da Klasse `CEditView` ist eine Ableitung von der Klasse `CView`, Objekte der Klasse `CEditView` mit Dokumenten und Dokumentvorlagen verwendet werden kann.  
  
 Jeder `CEditView` sein eigenes Objekt globaler Speicher Text Steuerelements beibehalten wird. Ihre Anwendung kann eine beliebige Anzahl von haben `CEditView` Objekte.  
  
 Erstellen von Objekten des Typs `CEditView` Sie ggf. ein Bearbeitungsfenster mit der zusätzlichen Funktionalität, die oben aufgeführten oder einfachen Text-Editor-Funktionen verwendet werden soll. Ein `CEditView` Objekt einnehmen kann den gesamten Clientbereich eines Fensters. Leiten Sie eigene Klassen von `CEditView` hinzufügen oder ändern die grundlegende Funktionen oder Klassen deklarieren, die eine Dokumentvorlage hinzugefügt werden können.  
  
 Die standardmäßige Implementierung der Klasse `CEditView` behandelt die folgenden Befehle: **ID_EDIT_SELECT_ALL**, **ID_EDIT_FIND**, **ID_EDIT_REPLACE**, **ID_EDIT_REPEAT**, und **ID_FILE_PRINT**.  
  
 Die Standard-Zeichen-Grenze für `CEditView` ist (1024 \* 1024-1 = 1048575). Dies kann geändert werden, durch Aufrufen der **EM_LIMITTEXT** Funktion der zugrunde liegenden edit-Steuerelement. Allerdings die Grenzwerte unterscheiden sich je nach Betriebssystem und der Typ des Bearbeitungssteuerelements (einfach oder mehrzeiligen). Weitere Informationen zu diesen Einschränkungen finden Sie unter [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Um diese Beschränkung im Steuerelement zu ändern, überschreiben die `OnCreate()` für Funktion Ihre `CEditView` Klasse, und fügen Sie die folgende Codezeile:  
  
 [!code-cpp[NVC_MFCDocView&#65;](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 Objekte vom Typ `CEditView` (oder von abgeleiteten Typen `CEditView`) weisen die folgenden Einschränkungen:  
  
- `CEditView`implementiert nicht "true" Was Sie sehen, ist das Ergebnis (WYSIWYG) bearbeiten. Eine Auswahl zwischen Lesbarkeit auf dem Bildschirm und übereinstimmende Druckausgabe, `CEditView` opts für den Bildschirm zu lesen.  
  
- `CEditView`Text kann in nur einer einzigen Schriftart angezeigt werden. Es wird keine besondere Formatierung unterstützt. Finden Sie unter Klasse [CRichEditView](../../mfc/reference/cricheditview-class.md) für verbesserte Funktionen.  
  
-   Die Größe des Texts einer `CEditView` darf ist begrenzt. Die Beschränkung sind die gleichen wie für die `CEdit` Steuerelement.  
  
 Weitere Informationen zu `CEditView`, finden Sie unter [abgeleiteten Ansicht Klassen in MFC verfügbare](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="a-nameceditviewa--ceditviewceditview"></a><a name="ceditview"></a>CEditView::CEditView  
 Konstruiert ein Objekt vom Typ `CEditView`.  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie die [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) funktionieren, bevor das Bearbeitungssteuerelement verwendet wird. Bei der Ableitung einer Klasse von `CEditView` und hinzuzufügen, die Vorlage mit `CWinApp::AddDocTemplate`, das Framework beide dieser Konstruktor aufruft und die **erstellen** Funktion.  
  
##  <a name="a-namedwstyledefaulta--ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>CEditView::dwStyleDefault  
 Enthält den Standardstil der `CEditView` Objekt.  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>Hinweise  
 Übergeben dieses statische Element als das `dwStyle` Parameter von der **erstellen** -Funktion das Standardformat für Abrufen der `CEditView` Objekt.  
  
##  <a name="a-namefindtexta--ceditviewfindtext"></a><a name="findtext"></a>CEditView::FindText  
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
 Gibt die Richtung der Suche. Wenn **TRUE**, die Suche am Ende des Puffers erfolgt. Wenn **FALSE**, die Suche am Anfang des Puffers erfolgt.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn **TRUE**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **FALSE**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der zu durchsuchende Text gefunden wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion sucht den Text im Puffer für den angegebenen Text `lpszFind`, beginnend bei der aktuellen Auswahl in der angegebenen Richtung `bNext`, und mit Groß-und Kleinschreibung der angegebenen `bCase`. Wenn der Text gefunden wird, legt die Auswahl auf den gefundenen Text fest und gibt einen Wert ungleich NULL zurück. Wenn der Text nicht gefunden wird, gibt die Funktion 0 zurück.  
  
 Brauchen Sie normalerweise rufen Sie die `FindText` funktionieren, wenn Sie außer Kraft setzen `OnFindNext`, welche `FindText`.  
  
##  <a name="a-namegetbufferlengtha--ceditviewgetbufferlength"></a><a name="getbufferlength"></a>CEditView::GetBufferLength  
 Rufen Sie diese Memberfunktion, um die Anzahl der Zeichen in das Bearbeitungssteuerelement Puffer nicht einschließlich des null-Abschlusszeichens zurzeit zu erhalten.  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge im Puffer.  
  
##  <a name="a-namegeteditctrla--ceditviewgeteditctrl"></a><a name="geteditctrl"></a>CEditView::GetEditCtrl  
 Rufen Sie `GetEditCtrl` zum Abrufen eines Verweises auf das Steuerelement zum Bearbeiten von der Bearbeitungsansicht verwendet.  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein `CEdit`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Steuerelement ist vom Typ [CEdit](../../mfc/reference/cedit-class.md), sodass Sie direkt mit der Windows-Bearbeitungssteuerelements bearbeiten, können die `CEdit` Memberfunktionen.  
  
> [!CAUTION]
>  Mithilfe der `CEdit` -Objekt kann ändern den Status des zugrunde liegenden Windows-edit-Steuerelement. Beispielsweise sollten Sie nicht mit Einstellungen auf der Registerkarte ändern die [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) funktionieren, da `CEditView` speichert diese Einstellungen für die Verwendung sowohl in das Steuerelement zum Bearbeiten und drucken. Verwenden Sie stattdessen [CEditView::SetTabStops](#settabstops).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#66;](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="a-namegetprinterfonta--ceditviewgetprinterfont"></a><a name="getprinterfont"></a>CEditView::GetPrinterFont  
 Rufen Sie `GetPrinterFont` um einen Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) -Objekt, das die aktuelle Druckerschriftart beschreibt.  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CFont` Objekt, das die aktuelle Druckerschriftart; angibt. **NULL** , wenn die Druckerschriftart nicht festgelegt wurde. Der Zeiger kann temporär sein und sollte nicht für eine spätere Verwendung gespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Druckerschriftart nicht, Drucken Verhalten der Standardeinstellung festgelegt wurde die `CEditView` Klasse dieselbe Schriftart für die Anzeige mit gedruckt wird.  
  
 Verwenden Sie diese Funktion, um die aktuelle Druckerschriftart zu bestimmen. Ist dies nicht der gewünschte Druckerschriftart, verwenden [CEditView::SetPrinterFont](#setprinterfont) ändern.  
  
##  <a name="a-namegetselectedtexta--ceditviewgetselectedtext"></a><a name="getselectedtext"></a>CEditView::GetSelectedText  
 Rufen Sie `GetSelectedText` kopiert den ausgewählten Text in ein `CString` Objekt bis zum Ende der Auswahl oder das Zeichen vor dem ersten Wagenrücklauf-Zeichen in der Auswahl.  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strResult`  
 Ein Verweis auf die `CString` -Objekt, das den ausgewählten Text zu erhalten.  
  
##  <a name="a-namelockbuffera--ceditviewlockbuffer"></a><a name="lockbuffer"></a>CEditView::LockBuffer  
 Rufen Sie diese Memberfunktion, um einen Zeiger auf den Puffer zu erhalten. Der Puffer sollte nicht geändert werden.  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Steuerelement zum Bearbeiten des Puffers.  
  
##  <a name="a-nameonfindnexta--ceditviewonfindnext"></a><a name="onfindnext"></a>CEditView::OnFindNext  
 Durchsucht den Text in den Puffer für den angegebenen Text `lpszFind`, in der angegebenen Richtung `bNext`, mit Groß-und Kleinschreibung der angegebenen `bCase`.  
  
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
 Gibt die Richtung der Suche. Wenn **TRUE**, die Suche am Ende des Puffers erfolgt. Wenn **FALSE**, die Suche am Anfang des Puffers erfolgt.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn **TRUE**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **FALSE**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
### <a name="remarks"></a>Hinweise  
 Die Suche beginnt am Anfang der aktuellen Auswahl und erfolgt über einen Aufruf von [FindText](#findtext). In der Standardimplementierung `OnFindNext` Aufrufe [OnTextNotFound](#ontextnotfound) , wenn der Text nicht gefunden wird.  
  
 Überschreiben Sie `OnFindNext` ändern eine `CEditView`-abgeleitetes Objekt sucht nach Text. `CEditView`Ruft `OnFindNext` bei Betätigung die Schaltfläche Weitersuchen im Dialogfeld standard suchen.  
  
##  <a name="a-nameonreplacealla--ceditviewonreplaceall"></a><a name="onreplaceall"></a>CEditView::OnReplaceAll  
 `CEditView`Aufrufe `OnReplaceAll` Wenn der Benutzer die Schaltfläche Alle ersetzen im Dialogfeld standard ersetzen auswählt.  
  
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
 Gibt an, ob die Suche Groß-/Kleinschreibung beachtet wird. Wenn **TRUE**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **FALSE**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
### <a name="remarks"></a>Hinweise  
 `OnReplaceAll`durchsucht den Text in den Puffer für den angegebenen Text `lpszFind`, mit Groß-und Kleinschreibung der angegebenen `bCase`. Die Suche beginnt am Anfang der aktuellen Auswahl. Bei jedem der zu durchsuchende Text gefunden wird, wird diese Funktion ersetzt, Vorkommen des Texts mit den angegebenen Text `lpszReplace`. Die Suche erfolgt durch einen Aufruf von [FindText](#findtext). In der Standardimplementierung [OnTextNotFound](#ontextnotfound) wird aufgerufen, wenn der Text nicht gefunden wird.  
  
 Wenn die aktuelle Auswahl nicht übereinstimmen `lpszFind`, die Auswahl wird auf das erste Vorkommen des angegebenen Texts aktualisiert `lpszFind` und ein ersetzen wird nicht ausgeführt. Dies ermöglicht es dem Benutzer zu bestätigen, dass dies Was möchten sie tun, bei die Auswahl der zu ersetzende Text nicht übereinstimmt.  
  
 Überschreiben Sie `OnReplaceAll` ändern eine `CEditView`-abgeleitetes Objekt ersetzt Text.  
  
##  <a name="a-nameonreplacesela--ceditviewonreplacesel"></a><a name="onreplacesel"></a>CEditView::OnReplaceSel  
 `CEditView`Ruft `OnReplaceSel` bei der Auswahl "ersetzen" in das Standarddialogfeld ersetzen.  
  
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
 Gibt die Richtung der Suche. Wenn **TRUE**, die Suche am Ende des Puffers erfolgt. Wenn **FALSE**, die Suche am Anfang des Puffers erfolgt.  
  
 `bCase`  
 Gibt an, ob es sich bei der Suche die Groß-/Kleinschreibung beachtet wird. Wenn **TRUE**, wird bei der Suche die Groß-/Kleinschreibung beachtet. Wenn **FALSE**, die Suche ist nicht in der Groß-/Kleinschreibung beachtet.  
  
 `lpszReplace`  
 Der Text, der gefundene Text ersetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sucht nach dem Ersetzen der Auswahl, den Text im Puffer nach dem nächsten Vorkommen des angegebenen Texts `lpszFind`, in der angegebenen Richtung `bNext`, mit Groß-und Kleinschreibung der angegebenen `bCase`. Die Suche erfolgt durch einen Aufruf von [FindText](#findtext). Wenn der Text nicht gefunden wird, [OnTextNotFound](#ontextnotfound) aufgerufen wird.  
  
 Überschreiben Sie `OnReplaceSel` Ändern einer `CEditView`-abgeleitetes Objekt ersetzt den markierten Text.  
  
##  <a name="a-nameontextnotfounda--ceditviewontextnotfound"></a><a name="ontextnotfound"></a>CEditView::OnTextNotFound  
 Überschreiben Sie diese Funktion, um die Windows-Funktion ruft die standardmäßige Implementierung ändern **MessageBeep**.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFind`  
 Der Text gefunden werden.  
  
##  <a name="a-nameprintinsiderecta--ceditviewprintinsiderect"></a><a name="printinsiderect"></a>CEditView::PrintInsideRect  
 Rufen Sie `PrintInsideRect` zum Drucken von Text im angegebenen Rechteck *RectLayout*.  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Drucker-Gerätekontext.  
  
 *rectLayout*  
 Ein Verweis auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT-Struktur](../../mfc/reference/rect-structure1.md) angeben Rechteck, in dem der Text gerendert werden.  
  
 `nIndexStart`  
 Der Index innerhalb des Puffers des ersten Zeichens gerendert werden soll.  
  
 `nIndexStop`  
 Der Index innerhalb des Puffers des Zeichens hinter dem letzten Zeichen gerendert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des nächsten Zeichens gedruckt werden (d. h. das Zeichen nach dem letzten Zeichen dargestellt).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `CEditView` -Steuerelement verfügt nicht über das Format **ES_AUTOHSCROLL**, Text innerhalb des Rechtecks Rendering umbrochen wird. Wenn das Steuerelement den Stil besitzt **ES_AUTOHSCROLL**, der Text wird am rechten Rand des Rechtecks abgeschnitten.  
  
 Die **rect.bottom** Element von der *RectLayout* Objekt geändert, sodass das Rechteck Dimensionen den Teil der ursprünglichen Rechteck definieren, der durch den Text belegt wird.  
  
##  <a name="a-nameserializerawa--ceditviewserializeraw"></a><a name="serializeraw"></a>SerializeRaw  
 Rufen Sie `SerializeRaw` haben eine `CArchive` Objekt lesen oder Schreiben Sie den Text in das `CEditView` Objekt in eine Textdatei.  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Ein Verweis auf die `CArchive` -Objekt, das den serialisierten Text gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 `SerializeRaw`unterscheidet sich von `CEditView`die interne Implementierung der `Serialize` , liest und nur den Text schreibt ohne Beschreibung-Objekts Daten vor.  
  
##  <a name="a-namesetprinterfonta--ceditviewsetprinterfont"></a><a name="setprinterfont"></a>CEditView::SetPrinterFont  
 Rufen Sie `SetPrinterFont` für die Druckerschriftart festzulegen, der vom angegebenen Schriftart `pFont`.  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 Ein Zeiger auf ein Objekt vom Typ `CFont`. Wenn **NULL**, die Schriftart für den Druck basiert auf der Systemschriftart.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Ansicht immer eine bestimmte Schriftart zum Drucken verwenden möchten, fügen Sie einen Aufruf von `SetPrinterFont` in Ihrer Klasse `OnPreparePrinting` Funktion. Diese virtuelle Funktion wird aufgerufen, bevor gedruckt wird, damit die Änderung der Schriftart stattfindet, bevor Sie den Inhalt der Ansicht gedruckt werden.  
  
##  <a name="a-namesettabstopsa--ceditviewsettabstops"></a><a name="settabstops"></a>CEditView::SetTabStops  
 Rufen Sie diese Funktion zum Festlegen von Tabstopps zum Anzeigen und drucken.  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>Parameter  
 `nTabStops`  
 Die Breite des einzelnen Tabstopps in Dialogeinheiten.  
  
### <a name="remarks"></a>Hinweise  
 Nur eine einzelne Tabstopp Breite wird unterstützt. ( `CEdit` Objekte unterstützen mehrere Tabulatorposition.) Breite sind im Dialogfeld Einheiten&1; /&4;, der die durchschnittliche Zeichenbreite gleich (basierend auf Groß- und Kleinschreibung nur alphabetische Zeichen) der Schriftart zum Zeitpunkt der drucken oder anzeigen. Verwenden Sie keine `CEdit::SetTabStops` da `CEditView` muss Zwischenspeichern den Tabstopp Wert.  
  
 Diese Funktion ändert nur die Registerkarten des Objekts, für das es aufgerufen wird. So ändern Sie die Registerkarte nicht mehr für die einzelnen `CEditView` -Objekts in der Anwendung, des Objekts aufrufen `SetTabStops` Funktion.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment wird die Tabstopps im Steuerelement in jeder vierten Zeichen durch Messen sorgfältig die Schriftart, die das Steuerelement verwendet.  
  
 [!code-cpp[NVC_MFCDocView&#67;](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="a-nameunlockbuffera--ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>CEditView::UnlockBuffer  
 Rufen Sie diese Memberfunktion um den Puffer zu entsperren.  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `UnlockBuffer` Sie nach dem Verwenden des zurückgegebene Zeigers [LockBuffer](#lockbuffer).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel SUPERPAD](../../visual-cpp-samples.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)

