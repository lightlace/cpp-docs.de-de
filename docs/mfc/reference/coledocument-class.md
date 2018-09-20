---
title: COleDocument-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
dev_langs:
- C++
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ec82a1f0aa025b8de938d30117032bd666d8bb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403174"
---
# <a name="coledocument-class"></a>COleDocument-Klasse

Die Basisklasse für OLE-Dokumente, die visuelle Bearbeitung unterstützen.

## <a name="syntax"></a>Syntax

```
class COleDocument : public CDocument
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|Erstellt ein `COleDocument`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|Fügt ein Element der Liste der Elemente im Dokument beibehalten.|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Legt das Drucken-Zielgerät für alle Clientelemente in das Dokument fest.|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Bewirkt, dass Dokumente mit dem OLE Structured Storage-Dateiformat gespeichert werden.|
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Gibt zurück, das OLE-Element, das derzeit direkt aktiv ist.|
|[COleDocument::GetNextClientItem](#getnextclientitem)|Ruft das nächste Clientelement durchlaufen werden können.|
|[COleDocument::GetNextItem](#getnextitem)|Ruft das nächste Dokumentelement durchlaufen werden können.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|Ruft das nächste Element der Server durchlaufen werden können.|
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Gibt das primäre ausgewählte OLE-Element im Dokument zurück.|
|[COleDocument::GetStartPosition](#getstartposition)|Ruft die erste Position, ab der Iteration ab.|
|[COleDocument::HasBlankItems](#hasblankitems)|Überprüft, ob leere Elemente im Dokument.|
|[COleDocument::OnShowViews](#onshowviews)|Wird aufgerufen, wenn das Dokument wird, sichtbar oder unsichtbar.|
|[COleDocument::RemoveItem](#removeitem)|Entfernt ein Element aus der Liste der Elemente im Dokument beibehalten.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Das Dokument markiert, als geändert, wenn keines der enthaltenen OLE-Elemente geändert wurden.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Behandelt Ereignisse, die in den Kontextmenübefehl von "Symbol ändern".|
|[COleDocument::OnEditConvert](#oneditconvert)|Übernimmt die Konvertierung eines eingebetteten oder verknüpften Objekts von einem Typ in einen anderen.|
|[COleDocument::OnEditLinks](#oneditlinks)|Behandelt Ereignisse, die im Befehl Links auf das Menü "Bearbeiten".|
|[COleDocument::OnFileSendMail](#onfilesendmail)|Sendet eine e-Mail-Nachricht mit dem Dokument angefügt.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Wird aufgerufen, durch das Framework die Befehlsbenutzeroberfläche, für die Bearbeitung/Änderung Symbol Menüoption zu aktualisieren.|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Wird aufgerufen, durch das Framework die Befehlsbenutzeroberfläche, für die Menüoption Bearbeitungslinks/zu aktualisieren.|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Wird aufgerufen, durch das Framework so aktualisieren Sie die Befehlsbenutzeroberfläche für die Bearbeitung / *ObjectName* Menüoption und das Verb Untermenü zugegriffen bearbeiten / *ObjectName*.|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Wird aufgerufen, durch das Framework die Befehlsbenutzeroberfläche, für die Inhalte einfügen Menüoption zu aktualisieren.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Wird aufgerufen, durch das Framework die Befehlsbenutzeroberfläche, für die einfügen-Menüoption zu aktualisieren.|

## <a name="remarks"></a>Hinweise

`COleDocument` stammt aus `CDocument`, wodurch Ihre OLE-Anwendungen verwenden die Dokument-/Ansichtarchitektur, die von der Microsoft Foundation Class-Bibliothek bereitgestellt.

`COleDocument` behandelt ein Dokument als eine Auflistung von [CDocItem](../../mfc/reference/cdocitem-class.md) Objekte OLE-Elemente verarbeitet werden. Container und Server-Anwendungen erfordern so eine Architektur, da ihre Dokumente können OLE-Elemente enthalten sein müssen. Die [COleServerItem](../../mfc/reference/coleserveritem-class.md) und [COleClientItem](../../mfc/reference/coleclientitem-class.md) sowohl von abgeleiteten Klassen `CDocItem`, verwalten Sie die Interaktionen zwischen Anwendungen und OLE-Elementen.

Wenn Sie eine einfache Container-Anwendung schreiben, leiten Sie die Dokumentklasse aus `COleDocument`. Wenn Sie eine containeranwendung schreiben, die unterstützt wird, auf die eingebetteten Elemente enthalten die Dokumente verknüpfen, leiten Sie die Dokumentklasse aus [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). Wenn Sie einen Server-Anwendung oder Kombination aus Container/Server schreiben, leiten Sie die Dokumentklasse aus [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc` und `COleServerDoc` davon abgeleitet sind `COleDocument`, sodass diese Klassen, die in verfügbaren Dienste erben `COleDocument` und `CDocument`.

Verwendung von `COleDocument`, eine Klasse ableiten, und fügen Sie Funktionen zum Verwalten der Anwendung nicht-OLE-Daten als auch eingebettete oder verknüpfte Elemente hinzu. Wenn Sie definieren `CDocItem`-abgeleiteten Klassen zum Speichern von systemeigenen Daten der Anwendung, können Sie die standardmäßige Implementierung von definierten `COleDocument` Ihre OLE und nicht-OLE-Daten zu speichern. Sie können auch Ihren eigenen Datenstrukturen zum Speichern Ihrer Daten nicht OLE getrennt von der OLE-Elementen gestalten. Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...

`CDocument` unterstützt das das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. `COleDocument` wurde aktualisiert, [OnFileSendMail](#onfilesendmail) Verbunddokumente ordnungsgemäß zu behandeln. Weitere Informationen finden Sie in den Artikeln [MAPI](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md)...

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="additem"></a>  COleDocument::AddItem

Rufen Sie diese Funktion ein Element zum Dokument hinzuzufügen.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das Dokumentelement hinzugefügt wird.

### <a name="remarks"></a>Hinweise

Sie müssen nicht explizit aufrufen dieser Funktion, wenn sie, durch aufgerufen wird die `COleClientItem` oder `COleServerItem` Konstruktor, der einen Zeiger auf ein Dokument akzeptiert.

##  <a name="applyprintdevice"></a>  COleDocument::ApplyPrintDevice

Mit dieser Funktion können Sie ändern das Drucken-Zielgerät für alle eingebetteten [COleClientItem](../../mfc/reference/coleclientitem-class.md) Elemente in Ihrer Anwendung Containerdokument.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Parameter

*ptd*<br/>
Zeiger auf eine `DVTARGETDEVICE` Datenstruktur, die Informationen über das neue Gerät für die Print-Ziel enthält. NULL kann sein.

*PPD*<br/>
Zeiger auf eine `PRINTDLG` Datenstruktur, die Informationen über das neue Gerät für die Print-Ziel enthält. NULL kann sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion aktualisiert das Gerät drucken-Ziel für alle Elemente jedoch den Presentation-Cache für diese Elemente werden nicht aktualisiert. Rufen Sie zum Aktualisieren der Präsentation-Cache nach einem Element [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).

Die Argumente für diese Funktion enthalten Informationen, die OLE verwendet, um das Gerät zu identifizieren. Die [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Struktur enthält Informationen, die von Windows verwendet, um das allgemeine Drucken-Dialogfeld zu initialisieren. Nachdem der Benutzer das Dialogfeld geschlossen wird, gibt Windows Informationen zu der Auswahl des Benutzers in dieser Struktur zurück. Die `m_pd` Mitglied einer [CPrintDialog](../../mfc/reference/cprintdialog-class.md) Objekt ist ein `PRINTDLG` Struktur.

Weitere Informationen finden Sie unter den [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Struktur im Windows SDK.

Weitere Informationen finden Sie unter den [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) Struktur im Windows SDK.

##  <a name="coledocument"></a>  COleDocument::COleDocument

Erstellt ein `COleDocument`-Objekt.

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>  COleDocument::EnableCompoundFile

Rufen Sie diese Funktion, wenn das Dokument, das zusammengesetzte-Dateiformat gespeichert werden soll.

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
Gibt an, ob die Verbunddatei-Unterstützung aktiviert oder deaktiviert ist.

### <a name="remarks"></a>Hinweise

Dies ist auch strukturierten Speicher bezeichnet. Rufen Sie diese Funktion in der Regel aus dem Konstruktor Ihrer `COleDocument`-abgeleitete Klasse. Weitere Informationen zu Verbunddokumente, finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...

Wenn Sie diese Memberfunktion nicht aufrufen, werden Dokumente in einem nicht strukturierten ("") Flatfile-Format gespeichert werden.

Nachdem Verbunddatei-Unterstützung aktiviert oder für ein Dokument deaktiviert ist, sollte die Einstellung nicht während des Dokuments Lebensdauer geändert werden.

##  <a name="getinplaceactiveitem"></a>  COleDocument::GetInPlaceActiveItem

Aufruf dieser Funktion zum Abrufen des OLE-Element ist derzeit aktiviert, direkt in das Rahmenfenster, das mit der Ansicht identifizierte *aufnehmen*.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
Zeiger auf das Fenster, in dem das Containerdokument angezeigt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die einzelnen, direkte aktive OLE-Element; NULL, wenn keine OLE-Element derzeit im Zustand "aktiv" in-Place ".

##  <a name="getnextclientitem"></a>  COleDocument::GetNextClientItem

Rufen Sie diese Funktion, um den Client-Elementen in Ihrem Dokument zugreifen.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Ein Verweis auf eine POSITION Wert festgelegt, durch einen vorherigen Aufruf von `GetNextClientItem`; der erste Wert wird zurückgegeben, durch die `GetStartPosition` Member-Funktion.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den nächsten Client Element im Dokument oder NULL, wenn keine weiteren Clientelemente vorhanden sind.

### <a name="remarks"></a>Hinweise

Nach jedem Aufruf, den Wert der *pos* für das nächste Element in das Dokument, das möglicherweise oder ist möglicherweise eine Client-Element nicht festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>  COleDocument::GetNextItem

Rufen Sie diese Funktion, um alle Elemente in Ihrem Dokument zugreifen.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Ein Verweis auf eine POSITION Wert festgelegt, durch einen vorherigen Aufruf von `GetNextItem`; der erste Wert wird zurückgegeben, durch die `GetStartPosition` Member-Funktion.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Dokumentelement an der angegebenen Position.

### <a name="remarks"></a>Hinweise

Nach jedem Aufruf, den Wert der *pos* auf den Wert für die POSITION des nächsten Elements im Dokument festgelegt ist. Wenn das abgerufene Element das letzte Element im Dokument der neue Wert des *pos* ist NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>  COleDocument::GetNextServerItem

Rufen Sie diese Funktion, um den Server-Elementen in Ihrem Dokument zugreifen.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Ein Verweis auf eine POSITION Wert festgelegt, durch einen vorherigen Aufruf von `GetNextServerItem`; der erste Wert wird zurückgegeben, durch die `GetStartPosition` Member-Funktion.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den nächsten Server Element im Dokument oder NULL, wenn keine weiteren Serverelemente vorhanden sind.

### <a name="remarks"></a>Hinweise

Nach jedem Aufruf, den Wert der *pos* für das nächste Element in das Dokument, das möglicherweise oder ist möglicherweise kein Serverelement festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>  COleDocument::GetPrimarySelectedItem

Wird aufgerufen, durch das Framework zum Abrufen des aktuell ausgewählten OLE-Elements in der angegebenen Ansicht.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Parameter

*pView*<br/>
Zeiger auf die aktive Ansicht-Objekt, das das Dokument anzeigen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die einzelnen ausgewählt OLE-Element. NULL, wenn keine OLE-Elemente ausgewählt sind, oder wenn mehr als eine davon wird ausgewählt.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung sucht die Liste der enthaltenen OLE-Elemente für ein einzelnes ausgewähltes Element und gibt einen Zeiger darauf zurück. Wenn kein Element ausgewählt ist oder wenn mehr als ein Element ausgewählt ist, gibt die Funktion NULL zurück. Müssen Sie überschreiben die `CView::IsSelected` Member-Funktion in Ihrer Ansichtsklasse für diese Funktion funktioniert. Überschreiben Sie diese Funktion, wenn Sie über eine eigene Methode zum Speichern von enthaltenen OLE-Elemente verfügen.

##  <a name="getstartposition"></a>  COleDocument::GetStartPosition

Rufen Sie diese Funktion, um die Position des ersten Elements im Dokument abzurufen.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Positionswert, der mit dem Starten des Dokuments Elemente durchlaufen werden kann. NULL, wenn das Dokument keine Elemente enthält.

### <a name="remarks"></a>Hinweise

Übergeben Sie den zurückgegebenen Wert mit `GetNextItem`, `GetNextClientItem`, oder `GetNextServerItem`.

##  <a name="hasblankitems"></a>  COleDocument::HasBlankItems

Rufen Sie diese Funktion, um zu bestimmen, ob das Dokument keine leere Elemente enthält.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Dokument keine leere Elemente enthält; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein leeres Element ist ein, dessen Rechteck leer ist.

##  <a name="oneditchangeicon"></a>  COleDocument::OnEditChangeIcon

Zeigt das Dialogfeld "Symbol für das OLE-ändern", und ändert sich das Symbol, das aktuell ausgewählte OLE-Element auf das Symbol, die, das vom Benutzer im Dialogfeld ausgewählten, darstellt.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Hinweise

`OnEditChangeIcon` erstellt und startet eine `COleChangeIconDialog` Dialogfeld anderes Symbol.

##  <a name="oneditconvert"></a>  COleDocument::OnEditConvert

Zeigt das Dialogfeld OLE konvertieren und konvertiert oder aktiviert das aktuell ausgewählte OLE-Element, entsprechend der Auswahl des Benutzers in das Dialogfeld.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Hinweise

`OnEditConvert` erstellt und startet eine `COleConvertDialog` konvertieren (Dialogfeld).

Ein Beispiel der Konvertierung ist ein Microsoft Word-Dokument in ein Dokument in WordPad konvertiert.

##  <a name="oneditlinks"></a>  COleDocument::OnEditLinks

Zeigt das Dialogfeld OLE/Bearbeitungslinks.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Hinweise

`OnEditLinks` erstellt und startet eine `COleLinksDialog` Dialogfeld Links, die dem Benutzer ermöglicht, die verknüpften Objekte zu ändern.

##  <a name="onfilesendmail"></a>  COleDocument::OnFileSendMail

Sendet eine Nachricht über den residenten Mailhost (sofern vorhanden) mit dem Dokument als Anlage.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Hinweise

`OnFileSendMail` Aufrufe `OnSaveDocument` (Speichern) ohne Titel und geänderte Dokumente in eine temporäre Datei serialisiert werden soll, klicken Sie dann über e-Mail gesendet wird. Wenn das Dokument nicht geändert wurde, wird eine temporäre Datei ist nicht erforderlich; die ursprüngliche wird gesendet. `OnFileSendMail` Lädt MAPI32 an. DLL, wenn es nicht bereits geladen wurde.

Im Gegensatz zu die Implementierung der `OnFileSendMail` für `CDocument`, diese Funktion behandelt compound-Dateien ordnungsgemäß.

Weitere Informationen finden Sie unter den [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md) Artikel...

##  <a name="onshowviews"></a>  COleDocument::OnShowViews

Das Framework ruft diese Funktion nach des Dokuments Sichtbarkeit Änderungen des Ansichtszustands.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Parameter

*bVisible*<br/>
Gibt an, ob das Dokument sichtbar oder unsichtbar geworden ist.

### <a name="remarks"></a>Hinweise

Die Standardversion dieser Funktion hat keine Auswirkungen. Wenn die Anwendung spezielle Verarbeitung ausführen muss bei Änderung des Dokuments Sichtbarkeit überschreiben.

##  <a name="onupdateeditchangeicon"></a>  COleDocument::OnUpdateEditChangeIcon

Wird aufgerufen, durch das Framework den Befehl "Symbol ändern" auf das Menü "Bearbeiten" zu aktualisieren.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf eine `CCmdUI` Struktur, die Sie im Menü darstellt, die den Update-Befehl generiert. Ruft das Update der `Enable` Memberfunktion die `CCmdUI` Struktur über *nämlich pCmdUI* zum Aktualisieren der Benutzeroberfläche.

### <a name="remarks"></a>Hinweise

`OnUpdateEditChangeIcon` aktualisiert die Befehls Benutzeroberfläche, je nachdem, ob ein gültiges Symbol im Dokument vorhanden ist. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.

##  <a name="onupdateeditlinksmenu"></a>  COleDocument::OnUpdateEditLinksMenu

Wird aufgerufen, durch das Framework den Befehl "Links" auf das Menü "Bearbeiten" zu aktualisieren.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf eine `CCmdUI` Struktur, die Sie im Menü darstellt, die den Update-Befehl generiert. Ruft das Update der `Enable` Memberfunktion die `CCmdUI` Struktur über *nämlich pCmdUI* zum Aktualisieren der Benutzeroberfläche.

### <a name="remarks"></a>Hinweise

Beginnend mit dem ersten OLE-Element im Dokument `OnUpdateEditLinksMenu` greift auf jedes Element, das überprüft, ob das Element ein Link ist, und, wenn es sich um einen Link handelt, mit dem Befehl Links kann. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.

##  <a name="onupdateobjectverbmenu"></a>  COleDocument::OnUpdateObjectVerbMenu

Aufgerufen, um zu aktualisieren die *ObjectName* Befehl auf das Menü "Bearbeiten" und das Verb Untermenü aus zugegriffen der *ObjectName* Befehl, in denen *ObjectName* ist der Name des OLE-Objekts, die im Dokument eingebettet werden.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf eine `CCmdUI` Struktur, die Sie im Menü darstellt, die den Update-Befehl generiert. Ruft das Update der `Enable` Memberfunktion die `CCmdUI` Struktur über *nämlich pCmdUI* zum Aktualisieren der Benutzeroberfläche.

### <a name="remarks"></a>Hinweise

`OnUpdateObjectVerbMenu` Updates der *ObjectName* Benutzeroberfläche des Befehls, je nachdem, ob ein gültiges Objekt im Dokument vorhanden ist. Wenn ein Objekt vorhanden ist, die *ObjectName* Befehl auf das Menü "Bearbeiten" ist aktiviert. Wenn dieser Befehl aktiviert ist, wird das Verb-Untermenü angezeigt. Das Verb Untermenü enthält alle das Verbbefehle für das Objekt, z. B. bearbeiten, Eigenschaften und So weiter verfügbar. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.

##  <a name="onupdatepastelinkmenu"></a>  COleDocument::OnUpdatePasteLinkMenu

Wird aufgerufen, durch das Framework, um zu bestimmen, ob ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf eine `CCmdUI` Struktur, die Sie im Menü darstellt, die den Update-Befehl generiert. Ruft das Update der `Enable` Memberfunktion die `CCmdUI` Struktur über *nämlich pCmdUI* zum Aktualisieren der Benutzeroberfläche.

### <a name="remarks"></a>Hinweise

Die Inhalte einfügen Menübefehl aktiviert oder deaktiviert werden, je nachdem, ob das Element in das Dokument kann oder nicht eingefügt werden.

##  <a name="onupdatepastemenu"></a>  COleDocument::OnUpdatePasteMenu

Wird aufgerufen, durch das Framework, um festzustellen, ob es sich bei ein eingebetteten OLE-Element aus der Zwischenablage eingefügt werden kann.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parameter

*nämlich pCmdUI*<br/>
Ein Zeiger auf eine `CCmdUI` Struktur, die Sie im Menü darstellt, die den Update-Befehl generiert. Ruft das Update der `Enable` Memberfunktion die `CCmdUI` Struktur über *nämlich pCmdUI* zum Aktualisieren der Benutzeroberfläche.

### <a name="remarks"></a>Hinweise

Das Menü-Befehl "Einfügen" und die Schaltfläche sind aktiviert oder deaktiviert, je nachdem, ob das Element in das Dokument kann oder nicht eingefügt werden.

##  <a name="removeitem"></a>  COleDocument::RemoveItem

Rufen Sie diese Funktion, um ein Element aus dem Dokument zu entfernen.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Zeiger auf das Dokumentelement entfernt werden soll.

### <a name="remarks"></a>Hinweise

Sie in der Regel müssen nicht explizit aufrufen dieser Funktion; Sie wird aufgerufen, durch die Destruktoren für `COleClientItem` und `COleServerItem`.

##  <a name="updatemodifiedflag"></a>  COleDocument::UpdateModifiedFlag

Rufen Sie diese Funktion aus, um das Dokument zu markieren, als geändert, wenn keines der enthaltenen OLE-Elemente geändert wurden.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Hinweise

Dadurch wird das Framework fordert den Benutzer auf das Dokument zu speichern, bevor Sie geschlossen wird, auch wenn die systemeigenen Daten in das Dokument nicht geändert wurde.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-CONTAINER](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)<br/>
[CDocument-Klasse](../../mfc/reference/cdocument-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)



