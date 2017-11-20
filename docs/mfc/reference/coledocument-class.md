---
title: COleDocument Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 976f6845deb93dc8bf6a2e008de0d68fb62bfbb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="coledocument-class"></a>COleDocument-Klasse
Die Basisklasse für OLE-Dokumente, die visuelle Bearbeitung unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|Erstellt ein `COleDocument`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|Fügt ein Element der Liste der Elemente, die durch das Dokument beibehalten.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Legt die Print-Zielgerät für alle Clientelemente im Dokument fest.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Bewirkt, dass Dokumente mit dem OLE Structured Storage-Dateiformat gespeichert werden soll.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Gibt die OLE-Element, das derzeit direkt aktiv ist.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|Ruft das nächste Clientelement für die Iteration an.|  
|[COleDocument::GetNextItem](#getnextitem)|Ruft das nächste Dokumentelement für die Iteration an.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|Ruft das nächste Element der Server für die Iteration an.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Gibt die primäre ausgewählte OLE-Element im Dokument zurück.|  
|[COleDocument::GetStartPosition](#getstartposition)|Ruft die erste Position, ab der Iteration ab.|  
|[COleDocument::HasBlankItems](#hasblankitems)|Überprüft, ob leere Elemente im Dokument.|  
|[COleDocument::OnShowViews](#onshowviews)|Wird aufgerufen, wenn das Dokument wird, ein- oder ausgeblendet.|  
|[COleDocument::RemoveItem](#removeitem)|Entfernt ein Element aus der Liste der Elemente, die durch das Dokument beibehalten.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Markiert das Dokument an, wie geändert werden, wenn eine der enthaltenen OLE-Elemente geändert wurden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Verarbeitet Ereignisse in den Menübefehl "Symbol ändern".|  
|[COleDocument::OnEditConvert](#oneditconvert)|Übernimmt die Konvertierung eines Objekts eingebettete oder verknüpfte von einem Typ in einen anderen.|  
|[COleDocument::OnEditLinks](#oneditlinks)|Verarbeitet Ereignisse in den Links-Befehl im Menü Bearbeiten.|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|Sendet eine e-Mail-Nachricht mit dem Dokument angefügt.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Vom Framework aufgerufen wird, aktualisieren Sie den UI-Befehl für die Menüoption "Symbol bearbeiten/ändern".|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Wird aufgerufen, durch das Framework den UI-Befehl für die Menüoption Bearbeitungslinks/zu aktualisieren.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Wird aufgerufen, durch das Framework für die Bearbeitung der Befehlsbenutzeroberfläche aktualisiert / *ObjectName* Menüoption und das Verb Untermenü zugegriffen bearbeiten / *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Wird aufgerufen, durch das Framework den UI-Befehl für die Inhalte einfügen Menüoption zu aktualisieren.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Wird aufgerufen, durch das Framework den UI-Befehl für den Menü-Option "Einfügen" zu aktualisieren.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDocument`stammt aus **CDocument**, wodurch die OLE-Anwendungen verwenden die Dokument-/Ansichtarchitektur, die von der Microsoft Foundation Class-Bibliothek bereitgestellt.  
  
 `COleDocument`ein Dokument behandelt, als eine Auflistung von [CDocItem](../../mfc/reference/cdocitem-class.md) Objekte zum Behandeln von OLE-Elementen. Container und Server-Anwendungen erfordern solche Architektur, da ihre Dokumente OLE-Elemente enthalten können. Die [COleServerItem](../../mfc/reference/coleserveritem-class.md) und [COleClientItem](../../mfc/reference/coleclientitem-class.md) sowohl von abgeleiteten Klassen `CDocItem`, verwalten Sie die Interaktionen zwischen Anwendungen und OLE-Elemente.  
  
 Wenn Sie eine einfache Steuerelementcontainer-Anwendung schreiben, leiten Sie eine Dokumentklasse von `COleDocument`. Wenn Sie eine Steuerelementcontainer-Anwendung, die mit der eingebetteten Elemente durch ihre Dokumente verknüpfen unterstützt schreiben, leiten Sie eine Dokumentklasse von [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). Wenn Sie eine Server-Anwendung oder eine Kombination Container/Server schreiben, leiten Sie eine Dokumentklasse von [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc`und `COleServerDoc` abgeleitet sind `COleDocument`, sodass diese Klassen in die verfügbaren Dienste erben `COleDocument` und **CDocument**.  
  
 Mit `COleDocument`, eine Klasse ableiten und Funktionen zur Verwaltung von der Anwendungsverzeichnis nicht OLE-Daten als auch eingebettete oder verknüpfte Elemente hinzufügen. Wenn Sie definieren `CDocItem`-abgeleitete Klassen zum Speichern von systemeigenen Daten der Anwendung, können Sie die standardmäßige Implementierung durch definierten `COleDocument` zum Speichern Ihrer OLE und der nicht-OLE-Daten. Sie können auch eigene Datenstrukturen für das Speichern Ihrer Daten nicht OLE getrennt von der OLE-Elementen entwerfen. Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...  
  
 **CDocument** unterstützt das Dokument per e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. `COleDocument`wurde aktualisiert, [OnFileSendMail](#onfilesendmail) Verbunddokumente ordnungsgemäß zu behandeln. Weitere Informationen finden Sie in den Artikeln [MAPI](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="additem"></a>COleDocument::AddItem  
 Mit dieser Funktion wird zum Hinzufügen eines Elements zum Dokument.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Dokumentelement hinzugefügt wird.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen nicht diese Funktion explizit aufrufen, wenn sie aufgerufen wird, indem Sie die `COleClientItem` oder `COleServerItem` Konstruktor, der einen Zeiger auf ein Dokument akzeptiert.  
  
##  <a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 Mit dieser Funktion wird so ändern Sie das Drucken-Zielgerät für alle eingebetteten [COleClientItem](../../mfc/reference/coleclientitem-class.md) Elemente in Ihrer Anwendung Containerdokument.  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parameter  
 `ptd`  
 Zeiger auf eine **DVTARGETDEVICE** Datenstruktur, die Informationen zu dem neuen Druckserver Zielgerät enthält. Kann **NULL**.  
  
 `ppd`  
 Zeiger auf eine **PRINTDLG** Datenstruktur, die Informationen zu dem neuen Druckserver Zielgerät enthält. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert die Print-Zielgerät für alle Elemente jedoch Präsentation Cache für diese Elemente werden nicht aktualisiert. Um die Präsentation Cache nach einem Element zu aktualisieren, rufen [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).  
  
 Die Argumente für diese Funktion enthalten Informationen, die OLE verwendet, um das Zielgerät zu identifizieren. Die [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Struktur enthält Informationen, die von Windows verwendet, um das allgemeine Drucken-Dialogfeld zu initialisieren. Nachdem der Benutzer das Dialogfeld geschlossen wurde, gibt Windows Informationen zur Auswahl des Benutzers in dieser Struktur zurück. Die `m_pd` Mitglied einer [CPrintDialog](../../mfc/reference/cprintdialog-class.md) Objekt ist ein **PRINTDLG** Struktur.  
  
 Weitere Informationen finden Sie unter der [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Struktur im Windows SDK.  
  
 Weitere Informationen finden Sie unter der [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Struktur im Windows SDK.  
  
##  <a name="coledocument"></a>COleDocument::COleDocument  
 Erstellt ein `COleDocument`-Objekt.  
  
```  
COleDocument();
```  
  
##  <a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 Rufen Sie diese Funktion, wenn das Dokument mithilfe der Compound-Dateiformat gespeichert werden soll.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob Verbunddatei-Unterstützung aktiviert oder deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird auch strukturierten Speicher bezeichnet. Mit dieser Funktion wird in der Regel vom Konstruktor der `COleDocument`-Klasse abgeleitet. Weitere Informationen zu Verbunddokumente, finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...  
  
 Wenn Sie diese Memberfunktion nicht aufrufen, werden Dokumente in einem nicht strukturierten ("") Flatfile-Format gespeichert.  
  
 Nachdem Verbunddatei-Unterstützung aktiviert oder für ein Dokument deaktiviert ist, sollte die Einstellung während der Lebensdauer des Dokuments nicht geändert werden.  
  
##  <a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 Aufruf dieser Funktion zum Abrufen des OLE Element, das derzeit aktiviert ist, direkt in das Rahmenfenster, enthält die Ansicht identifizierte `pWnd`.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das Containerdokument anzeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen, direkte aktive OLE-Element; **NULL** Falls kein OLE-Element gibt es derzeit im Zustand "in-Place aktiv" ist.  
  
##  <a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 Mit dieser Funktion wird wiederholt ausführen, um den Client-Elementen in Ihrem Dokument zugreifen.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Verweis auf eine **POSITION** festgelegten Wert, durch einen vorherigen Aufruf `GetNextClientItem`; der ursprüngliche Wert wird zurückgegeben, durch die `GetStartPosition` Memberfunktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Clientelement im Dokument oder **NULL** , wenn keine weitere Clientelemente vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Nach jedem Aufruf, der Wert des `pos` für das nächste Element in das Dokument, das möglicherweise oder möglicherweise eine Client-Element nicht festgelegt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="getnextitem"></a>COleDocument::GetNextItem  
 Mit dieser Funktion wird wiederholt ausführen, um jedes der Elemente in Ihrem Dokument zugreifen.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Verweis auf eine **POSITION** festgelegten Wert, durch einen vorherigen Aufruf `GetNextItem`; der ursprüngliche Wert wird zurückgegeben, durch die `GetStartPosition` Memberfunktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokumentelement an der angegebenen Position.  
  
### <a name="remarks"></a>Hinweise  
 Nach jedem Aufruf, der Wert der `pos` festgelegt ist, um die **POSITION** Wert, der das nächste Element im Dokument. Wenn das abgerufene Element das letzte Element im Dokument, der neue Wert des `pos` ist **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 Mit dieser Funktion wird wiederholt ausführen, um die Elemente in Ihrem Dokument zugreifen.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Verweis auf eine **POSITION** festgelegten Wert, durch einen vorherigen Aufruf `GetNextServerItem`; der ursprüngliche Wert wird zurückgegeben, durch die `GetStartPosition` Memberfunktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Serverelement im Dokument oder **NULL** , wenn keine weitere Serverelemente vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Nach jedem Aufruf, der Wert des `pos` für das nächste Element in das Dokument, das kann oder auch kein Serverelement festgelegt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 Wird aufgerufen, durch das Framework das aktuell ausgewählte OLE-Element in der angegebenen Ansicht abrufen.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pView`  
 Zeiger auf die aktive Ansicht-Objekt, das Dokument anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen ausgewählt OLE-Element. **NULL** Wenn keine OLE-Elemente ausgewählt sind oder wenn mehr als eine wurde ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sucht die Liste der enthaltenen OLE-Elemente für ein einzelnes ausgewähltes Element und gibt einen Zeiger darauf zurück. Wenn kein Element ausgewählt ist, oder wenn mehr als ein Element ausgewählt ist, die Funktion gibt **NULL**. Müssen Sie überschreiben die `CView::IsSelected` Memberfunktion in Ihrer Ansichtsklasse für diese Funktion ordnungsgemäß ausgeführt wird. Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode zum Speichern von enthaltenen OLE-Elemente haben.  
  
##  <a name="getstartposition"></a>COleDocument::GetStartPosition  
 Mit dieser Funktion wird um die Position des ersten Elements im Dokument zu erhalten.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** Wert, der verwendet werden kann, um zu beginnen, durchlaufen die Dokumentelemente; **NULL** Wenn das Dokument keine Elemente aufweist.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie den zurückgegebenen Wert `GetNextItem`, `GetNextClientItem`, oder `GetNextServerItem`.  
  
##  <a name="hasblankitems"></a>COleDocument::HasBlankItems  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Dokument keine leeren Elemente enthält.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument keine leeren Elemente enthält; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein leeres Element ist ein, deren Rechteck leer ist.  
  
##  <a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 Zeigt das Dialogfeld OLE "Symbol ändern", und ändert sich das Symbol, das aktuell ausgewählte OLE-Element darstellt, auf das Symbol, das der Benutzer im Dialogfeld auswählt.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnEditChangeIcon`erstellt und startet eine `COleChangeIconDialog` Dialogfeld "Symbol ändern".  
  
##  <a name="oneditconvert"></a>COleDocument::OnEditConvert  
 Zeigt das Dialogfeld OLE konvertieren und konvertiert oder aktiviert das aktuell ausgewählte OLE-Element, entsprechend der Auswahl des Benutzers im Dialogfeld.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnEditConvert`erstellt und startet eine `COleConvertDialog` konvertieren (Dialogfeld).  
  
 Ein Beispiel der Konvertierung ist ein Microsoft Word-Dokument in ein Dokument WordPad konvertieren.  
  
##  <a name="oneditlinks"></a>COleDocument::OnEditLinks  
 Zeigt das Dialogfeld OLE/Bearbeitungslinks.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnEditLinks`erstellt und startet eine `COleLinksDialog` Links (Dialogfeld), die dem Benutzer ermöglicht, verknüpfte Objekte zu ändern.  
  
##  <a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 Sendet eine Nachricht über den residenten Mailhost (sofern vorhanden) mit dem Dokument als Anlage.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnFileSendMail`Aufrufe `OnSaveDocument` (Speichern) neue und geänderte Dokumente in eine temporäre Datei zu serialisieren, die dann per e-Mail gesendet wird. Wenn das Dokument nicht geändert wurde, wird eine temporäre Datei nicht erforderlich. die ursprüngliche wird gesendet. `OnFileSendMail`Lädt MAPI32. DLL, wenn er nicht bereits geladen wurde.  
  
 Im Gegensatz zu der Implementierung des `OnFileSendMail` für **CDocument**, diese Funktion Verbunddateien ordnungsgemäß behandelt.  
  
 Weitere Informationen finden Sie unter der [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md) Artikel...  
  
##  <a name="onshowviews"></a>COleDocument::OnShowViews  
 Das Framework ruft diese Funktion nach dem das Dokument Sichtbarkeit Zustandsänderungen.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>Parameter  
 `bVisible`  
 Gibt an, ob das Dokument sichtbar oder unsichtbar geworden ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardversion von dieser Funktion wird keine Aktion ausgeführt. Wenn Ihre Anwendung keine besonderen verarbeiten ausführen muss, wenn das Dokument Sichtbarkeit ändert überschreiben.  
  
##  <a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 Vom Framework aufgerufen wird, aktualisieren Sie den Befehl "Symbol ändern" im Menü Bearbeiten.  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die im Menü darstellt, die den Updatebefehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 `OnUpdateEditChangeIcon`aktualisiert die Benutzeroberfläche des Befehls, je nachdem, ob ein gültiges Symbol im Dokument vorhanden ist. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.  
  
##  <a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 Vom Framework aufgerufen wird, aktualisieren Sie den Befehl "Links" im Menü Bearbeiten.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die im Menü darstellt, die den Updatebefehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 Beginnend mit dem ersten OLE-Element im Dokument `OnUpdateEditLinksMenu` greift auf jedes Element, das überprüft, ob das Element ein Link ist und, wenn es sich um einen Link handelt die Links-Befehl ermöglicht. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.  
  
##  <a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 Wird aufgerufen, durch das Framework beim Aktualisieren der *ObjectName* Befehl im Menü Bearbeiten und das Verb Untermenü aus zugegriffen der *ObjectName* Befehl, auf dem *ObjectName* ist der Name des OLE-Objekts, die in das Dokument eingebettet sind.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die im Menü darstellt, die den Updatebefehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 `OnUpdateObjectVerbMenu`Updates der *ObjectName* Benutzeroberfläche des Befehls, je nachdem, ob ein gültiges Objekt in das Dokument vorhanden ist. Wenn ein Objekt vorhanden ist, die *ObjectName* Befehl im Menü Bearbeiten ist aktiviert. Wenn dieser Menübefehl aktiviert ist, wird das Verb Untermenü angezeigt. Das Untermenü Verb enthält alle für das Objekt, z. B. bearbeiten, Eigenschaften und So weiter verfügbar Verbbefehle. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.  
  
##  <a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 Wird aufgerufen, durch das Framework, um zu bestimmen, ob ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die im Menü darstellt, die den Updatebefehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die Inhalte einfügen Menübefehl wird aktiviert oder deaktiviert, je nachdem, ob das Element in das Dokument kann oder nicht eingefügt werden.  
  
##  <a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 Wird aufgerufen, durch das Framework, um zu bestimmen, ob es sich bei ein eingebettetes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die im Menü darstellt, die den Updatebefehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 Der Menübefehl einfügen und die Schaltfläche sind aktiviert oder deaktiviert, je nachdem, ob das Element in das Dokument kann oder nicht eingefügt werden.  
  
##  <a name="removeitem"></a>COleDocument::RemoveItem  
 Rufen Sie diese Funktion, um ein Element aus dem Dokument zu entfernen.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Dokumentelement entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Sie in der Regel müssen nicht explizit aufrufen dieser Funktion; wird aufgerufen, indem Sie die Destruktoren für `COleClientItem` und `COleServerItem`.  
  
##  <a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 Rufen Sie diese Funktion, um das Dokument zu markieren, die geändert werden, wenn eine der enthaltenen OLE-Elemente geändert wurden.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies kann das Framework fordert den Benutzer auf das Dokument zu speichern, bevor Sie geschlossen wird, auch wenn die systemeigenen Daten im Dokument nicht geändert wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CONTAINER](../../visual-cpp-samples.md)   
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



