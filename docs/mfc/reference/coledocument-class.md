---
title: COleDocument Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocument
dev_langs:
- C++
helpviewer_keywords:
- COleDocument class
- OLE documents, base class
- OLE containers, client items
- visual editing, OLE document base class
- OLE documents
- documents, OLE
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
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
ms.openlocfilehash: 73bd1bc5c2c93e180b42a79cf23ab98360887c31
ms.lasthandoff: 02/24/2017

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
|[COleDocument::AddItem](#additem)|Fügt ein Element zur Liste der Elemente, die durch das Dokument beibehalten.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Legt das Drucken-Zielgerät für alle Clientelemente im Dokument fest.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Bewirkt, dass Dokumente mit dem OLE Structured Storage-Dateiformat gespeichert werden.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Gibt das OLE-Element, das derzeit in-Place aktiv ist.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|Ruft das nächste Clientelement durchlaufen.|  
|[COleDocument::GetNextItem](#getnextitem)|Ruft das nächste Dokumentelement durchlaufen werden können.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|Ruft das nächste Element der Server durchlaufen werden können.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Das primäre ausgewählte OLE-Element zurückgegeben im Dokument.|  
|[COleDocument::GetStartPosition](#getstartposition)|Ruft die erste Position, ab der Iteration ab.|  
|[COleDocument::HasBlankItems](#hasblankitems)|Überprüft, ob leere Objekte im Dokument.|  
|[COleDocument::OnShowViews](#onshowviews)|Wird aufgerufen, wenn das Dokument wird, sichtbar oder unsichtbar.|  
|[COleDocument::RemoveItem](#removeitem)|Entfernt ein Element aus der Liste der Elemente, die durch das Dokument verwaltet.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Markiert das Dokument an, als geändert, wenn eines der enthaltenen OLE-Elemente geändert wurden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Behandelt Ereignisse, die in den Menübefehl "Symbol ändern".|  
|[COleDocument::OnEditConvert](#oneditconvert)|Übernimmt die Konvertierung eines eingebetteten oder verknüpften Objekts von einem Typ in einen anderen.|  
|[COleDocument::OnEditLinks](#oneditlinks)|Behandelt Ereignisse, die in dem Befehl Verknüpfungen im Menü Bearbeiten.|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|Sendet eine e-Mail-Nachricht mit dem Dokument angefügt.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Aufgerufen, aktualisieren Sie den Befehl Benutzeroberfläche für die Option Symbol bearbeiten/ändern.|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Aufgerufen, um die Befehlsbenutzeroberfläche für die Menüoption Bearbeiten-Links zu aktualisieren.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Aufgerufen, die Befehlsbenutzeroberfläche für die Bearbeitung aktualisieren / *ObjectName* Menüoption und das Verb Untermenü Zugriff auf Bearbeiten / *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Aufgerufen, aktualisieren Sie den Befehl Benutzeroberfläche für die Option Inhalte einfügen.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Aufgerufen, aktualisieren Sie den Befehl Benutzeroberfläche für die Option einfügen.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDocument`stammt von **CDocument**, eine OLE-Anwendung von der Microsoft Foundation Class-Bibliothek bereitgestellte Dokument-/Ansichtarchitektur verwendet.  
  
 `COleDocument`behandelt ein Dokument als eine Auflistung von [CDocItem](../../mfc/reference/cdocitem-class.md) Objekte OLE-Elemente verarbeitet werden. Container und Server-Anwendungen erfordern eine solche Architektur, da ihre Dokumente OLE-Elemente enthalten können. Die [COleServerItem](../../mfc/reference/coleserveritem-class.md) und [COleClientItem](../../mfc/reference/coleclientitem-class.md) sowohl von abgeleiteten Klassen `CDocItem`, verwaltet die Interaktion zwischen OLE-Elemente.  
  
 Wenn Sie eine einfachen Steuerelementcontainer-Anwendung schreiben, leiten Sie die Dokumentklasse von `COleDocument`. Wenn Sie eine Steuerelementcontainer-Anwendung, die die eingebettete Elemente durch seine Dokumente verknüpfen unterstützt schreiben, leiten Sie eine Dokumentklasse von [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). Wenn Sie eine Server-Anwendung oder eine Kombination der Container/Server schreiben, leiten Sie die Dokumentklasse von [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc`und `COleServerDoc` abgeleitet sind `COleDocument`, sodass diese Klassen, die in verfügbaren Dienste erben `COleDocument` und **CDocument**.  
  
 Mit `COleDocument`, eine Klasse ableiten und Funktionen zur Verwaltung von der Anwendungsverzeichnis nicht-OLE-Daten als auch eingebettete oder verknüpfte Elemente hinzufügen. Wenn Sie definieren `CDocItem`-abgeleitete Klassen die Anwendung einheitlichen Daten speichern, können Sie die standardmäßige Implementierung definiert `COleDocument` zum Speichern Ihrer OLE und nicht-OLE-Daten. Sie können auch Ihren eigenen Datenstrukturen für das Speichern von nicht-OLE-Daten unabhängig von der OLE-Elemente entwerfen. Weitere Informationen finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...  
  
 **CDocument** unterstützt das Dokument über e-Mail senden, wenn e-Mail-Unterstützung (MAPI) vorhanden ist. `COleDocument`wurde aktualisiert, [OnFileSendMail](#onfilesendmail) Verbunddokumente ordnungsgemäß zu behandeln. Weitere Informationen finden Sie in den Artikeln [MAPI](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="a-nameadditema--coledocumentadditem"></a><a name="additem"></a>COleDocument::AddItem  
 Rufen Sie diese Funktion, um das Dokument ein Element hinzuzufügen.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Dokumentelement hinzugefügt wird.  
  
### <a name="remarks"></a>Hinweise  
 Sie brauchen diese Funktion explizit aufrufen, wenn sie aufgerufen wird, indem Sie die `COleClientItem` oder `COleServerItem` -Konstruktor, der einen Zeiger auf ein Dokument akzeptiert.  
  
##  <a name="a-nameapplyprintdevicea--coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 Rufen Sie diese Funktion zum Ändern der Print-Zielgerät für alle eingebetteten [COleClientItem](../../mfc/reference/coleclientitem-class.md) Elemente in Ihrer Anwendung Containerdokument.  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parameter  
 `ptd`  
 Zeiger auf eine **DVTARGETDEVICE** Datenstruktur, die Informationen über das neue Ziel drucken Gerät enthält. Kann **NULL**.  
  
 `ppd`  
 Zeiger auf eine **PRINTDLG** Datenstruktur, die Informationen über das neue Ziel drucken Gerät enthält. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert die Print-Zielgerät für alle Elemente jedoch Präsentation Cache für diese Elemente werden nicht aktualisiert. Um die Präsentation-Cache nach einem Element zu aktualisieren, rufen [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).  
  
 Die Argumente für diese Funktion enthalten Informationen, die OLE verwendet, um das Gerät zu identifizieren. Die [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Struktur enthält Informationen, die Windows verwendet, um das Standarddialogfeld Drucken zu initialisieren. Nachdem der Benutzer das Dialogfeld geschlossen wird, gibt Windows Informationen zur Auswahl des Benutzers in dieser Struktur zurück. Die `m_pd` Mitglied einer [CPrintDialog](../../mfc/reference/cprintdialog-class.md) -Objekt ist ein **PRINTDLG** Struktur.  
  
 Weitere Informationen finden Sie unter der [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter der [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecoledocumenta--coledocumentcoledocument"></a><a name="coledocument"></a>COleDocument::COleDocument  
 Erstellt ein `COleDocument`-Objekt.  
  
```  
COleDocument();
```  
  
##  <a name="a-nameenablecompoundfilea--coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 Rufen Sie diese Funktion, wenn das Dokument mit dem Compound-Dateiformat gespeichert werden soll.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob Verbunddatei-Unterstützung aktiviert oder deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Dies nennt man auch strukturierten Speicher. In der Regel rufen Sie diese Funktion vom Konstruktor der `COleDocument`-Klasse. Weitere Informationen über Verbunddokumente finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...  
  
 Wenn Sie nicht diese Member-Funktion aufrufen, werden Dokumente in einen nicht strukturierten ("") Flatfile-Format gespeichert werden.  
  
 Nachdem Verbunddatei-Unterstützung aktiviert oder für ein Dokument deaktiviert ist, sollte die Einstellung nicht während der Lebensdauer des Dokuments geändert werden.  
  
##  <a name="a-namegetinplaceactiveitema--coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 Aufruf dieser Funktion zum Abrufen des OLE Element, das derzeit aktiviert ist, direkt in das Rahmenfenster, das die Sicht identifizierten `pWnd`.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `pWnd`  
 Ein Zeiger auf das Fenster, das das Containerdokument angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen, direkte aktive OLE-Objekt; **NULL** Wenn kein OLE-Element derzeit im Zustand "in-Place aktiv".  
  
##  <a name="a-namegetnextclientitema--coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 Rufen Sie diese Funktion wiederholt auf, um die Clientelemente im Dokument zugreifen.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Einen Verweis auf eine **POSITION** Wert festgelegt, durch einen vorherigen Aufruf von `GetNextClientItem`; der anfängliche Wert wird zurückgegeben, durch die `GetStartPosition` Member-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Clientelement im Dokument oder **NULL** Wenn keine weitere Clientelemente vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Nach jedem Aufruf, der den Wert des `pos` für das nächste Element in das Dokument, das möglicherweise oder sind möglicherweise kein Clientelement festgelegt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#1;](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="a-namegetnextitema--coledocumentgetnextitem"></a><a name="getnextitem"></a>COleDocument::GetNextItem  
 Rufen Sie diese Funktion wiederholt auf, um jedes Element im Dokument zugreifen.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Einen Verweis auf eine **POSITION** Wert festgelegt, durch einen vorherigen Aufruf von `GetNextItem`; der anfängliche Wert wird zurückgegeben, durch die `GetStartPosition` Member-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Dokument oder ein Element an der angegebenen Position.  
  
### <a name="remarks"></a>Hinweise  
 Nach jedem Aufruf, der den Wert der `pos` wird festgelegt, um die **POSITION** Wert, der das nächste Element im Dokument. Wenn das abgerufene Element das letzte Element im Dokument der neue Wert der `pos` ist **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#2;](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="a-namegetnextserveritema--coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 Rufen Sie diese Funktion wiederholt auf, um die Elemente in Ihrem Dokument zugreifen.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Einen Verweis auf eine **POSITION** Wert festgelegt, durch einen vorherigen Aufruf von `GetNextServerItem`; der anfängliche Wert wird zurückgegeben, durch die `GetStartPosition` Member-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Serverelement im Dokument oder **NULL** Wenn keine weiteren Serverelemente vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Nach jedem Aufruf, der den Wert des `pos` für das nächste Element in das Dokument, das möglicherweise oder ist möglicherweise kein Serverelement festgelegt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleServer&#2;](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="a-namegetprimaryselecteditema--coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 Aufgerufen, um das aktuell ausgewählte OLE-Element in der angegebenen Ansicht abzurufen.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>Parameter  
 `pView`  
 Zeiger auf die aktive Ansicht-Objekt, das das Dokument anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen ausgewählt OLE-Element. **NULL** Wenn keine OLE-Elemente ausgewählt sind oder wenn mehrere ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sucht die Liste der enthaltenen OLE-Elemente für ein ausgewähltes Element und gibt einen Zeiger darauf zurück. Wenn kein Element ausgewählt ist, oder wenn mehr als ein Element ausgewählt ist, die Funktion gibt **NULL**. Müssen Sie überschreiben die `CView::IsSelected` -Memberfunktion der Ansichtsklasse für diese Funktion verwendet werden. Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode zum Speichern von enthaltenen OLE-Elemente verfügen.  
  
##  <a name="a-namegetstartpositiona--coledocumentgetstartposition"></a><a name="getstartposition"></a>COleDocument::GetStartPosition  
 Rufen Sie diese Funktion, um die Position des ersten Elements im Dokument abzurufen.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der zum Durchlaufen des Dokuments Elemente verwendet werden kann **NULL** Wenn das Dokument keine Elemente enthält.  
  
### <a name="remarks"></a>Hinweise  
 Übergeben Sie den zurückgegebenen Wert mit `GetNextItem`, `GetNextClientItem`, oder `GetNextServerItem`.  
  
##  <a name="a-namehasblankitemsa--coledocumenthasblankitems"></a><a name="hasblankitems"></a>COleDocument::HasBlankItems  
 Rufen Sie diese Funktion, um zu bestimmen, ob das Dokument leere Elemente enthält.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument leere Elemente enthält; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein leeres Element ist ein, dessen Rechteck leer ist.  
  
##  <a name="a-nameoneditchangeicona--coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 Zeigt das Dialogfeld OLE "Symbol ändern", und ändert sich das Symbol für das aktuell ausgewählte OLE-Element auf das Symbol, das der Benutzer im Dialogfeld auswählt.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnEditChangeIcon`erstellt und startet einen `COleChangeIconDialog` Dialogfeld "Symbol ändern".  
  
##  <a name="a-nameoneditconverta--coledocumentoneditconvert"></a><a name="oneditconvert"></a>COleDocument::OnEditConvert  
 Zeigt das Dialogfeld OLE konvertieren und konvertiert oder aktiviert das aktuell ausgewählte OLE-Element entsprechend der Auswahl des Benutzers im Dialogfeld.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnEditConvert`erstellt und startet einen `COleConvertDialog` konvertieren (Dialogfeld).  
  
 Ein Beispiel für die Konvertierung ist ein Microsoft Word-Dokument in ein WordPad-Dokument konvertieren.  
  
##  <a name="a-nameoneditlinksa--coledocumentoneditlinks"></a><a name="oneditlinks"></a>COleDocument::OnEditLinks  
 Zeigt das Dialogfeld OLE/Links zum Bearbeiten an.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnEditLinks`erstellt und startet einen `COleLinksDialog` Dialogfeld Links, die dem Benutzer ermöglicht, die verknüpften Objekte ändern.  
  
##  <a name="a-nameonfilesendmaila--coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 Sendet eine Nachricht über den residenten Mailhost (sofern vorhanden) mit dem Dokument als Anlage.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>Hinweise  
 `OnFileSendMail`Aufrufe `OnSaveDocument` (Speichern) neue und geänderte Dokumente in eine temporäre Datei serialisiert werden soll, die dann per e-Mail gesendet wird. Wenn das Dokument nicht geändert wurde, wird eine temporäre Datei nicht erforderlich. die ursprüngliche wird gesendet. `OnFileSendMail`Lädt MAPI32. DLL, wenn er nicht bereits geladen wurde.  
  
 Anders als bei der Implementierung des `OnFileSendMail` für **CDocument**, diese Funktion Verbunddateien ordnungsgemäß behandelt.  
  
 Weitere Informationen finden Sie unter der [MAPI-Themen](../../mfc/mapi.md) und [MAPI-Unterstützung in MFC](../../mfc/mapi-support-in-mfc.md) Artikel...  
  
##  <a name="a-nameonshowviewsa--coledocumentonshowviews"></a><a name="onshowviews"></a>COleDocument::OnShowViews  
 Das Framework ruft diese Funktion nach Sichtbarkeit des Dokuments Zustandsänderungen.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>Parameter  
 `bVisible`  
 Gibt an, ob das Dokument sichtbar oder unsichtbar geworden ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardversion von dieser Funktion hat keine Auswirkung. Wenn Ihre Anwendung ausführen muss spezielle Verarbeitungsschritte eine Änderung des Dokuments Sichtbarkeit überschreiben.  
  
##  <a name="a-nameonupdateeditchangeicona--coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 Vom Framework aufgerufen wird, aktualisieren Sie den Befehl "Symbol ändern" im Menü Bearbeiten.  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die das Menü darstellt, die den Update-Befehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 `OnUpdateEditChangeIcon`aktualisiert die Befehls Benutzeroberfläche, je nachdem, ob ein gültiges Symbol im Dokument vorhanden ist. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.  
  
##  <a name="a-nameonupdateeditlinksmenua--coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 Vom Framework aufgerufen wird, aktualisieren Sie die Links-Befehl im Menü Bearbeiten.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die das Menü darstellt, die den Update-Befehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 Beginnend mit dem ersten OLE-Element im Dokument `OnUpdateEditLinksMenu` greift auf jedes Element, das überprüft, ob das Element einen Link, und, ist dies eine Verknüpfung mit dem Befehl Links kann. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.  
  
##  <a name="a-nameonupdateobjectverbmenua--coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 Aufgerufen, zum Aktualisieren der *ObjectName* Befehl im Menü Bearbeiten und das Verb Untermenü aus zugegriffen der *ObjectName* Befehl, in dem *ObjectName* ist der Name des OLE-Objekts in das Dokument eingebettet.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die das Menü darstellt, die den Update-Befehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 `OnUpdateObjectVerbMenu`Updates der *ObjectName* Benutzeroberfläche des Befehls, je nachdem, ob ein gültiges Objekt im Dokument vorhanden ist. Wenn ein Objekt vorhanden ist, die *ObjectName* Befehl im Menü Bearbeiten aktiviert ist. Wenn dieser Befehl aktiviert ist, wird das Verb Untermenü angezeigt. Das Verb Untermenü enthält alle für das Objekt, z. B. bearbeiten, Eigenschaften usw. Verbbefehle. Überschreiben Sie diese Funktion, um das Verhalten zu ändern.  
  
##  <a name="a-nameonupdatepastelinkmenua--coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 Aufgerufen, um festzustellen, ob ein verknüpftes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die das Menü darstellt, die den Update-Befehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 Befehls im Menü Einfügen ist aktiviert oder deaktiviert werden, je nachdem, ob das Element in das Dokument kann oder nicht eingefügt werden.  
  
##  <a name="a-nameonupdatepastemenua--coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 Aufgerufen, um festzustellen, ob es sich bei ein eingebettetes OLE-Element aus der Zwischenablage eingefügt werden kann.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parameter  
 `pCmdUI`  
 Ein Zeiger auf eine `CCmdUI` -Struktur, die das Menü darstellt, die den Update-Befehl generiert. Ruft das Update der **aktivieren** Memberfunktion der `CCmdUI` Struktur über `pCmdUI` zum Aktualisieren der Benutzeroberfläche.  
  
### <a name="remarks"></a>Hinweise  
 Den Befehl Einfügen und die Schaltfläche sind aktiviert oder deaktiviert, je nachdem, ob das Element in das Dokument kann oder nicht eingefügt werden.  
  
##  <a name="a-nameremoveitema--coledocumentremoveitem"></a><a name="removeitem"></a>COleDocument::RemoveItem  
 Rufen Sie diese Funktion, um ein Element aus dem Dokument zu entfernen.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Dokument oder ein Element entfernt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Sie normalerweise müssen nicht diese Funktion explizit aufrufen. wird aufgerufen, indem die Destruktoren für `COleClientItem` und `COleServerItem`.  
  
##  <a name="a-nameupdatemodifiedflaga--coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 Rufen Sie diese Funktion, um das Dokument zu markieren, die geändert werden, wenn eines der enthaltenen OLE-Elemente geändert wurden.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>Hinweise  
 Dadurch kann das Framework den Benutzer auffordern, das Dokument zu speichern, bevor Sie geschlossen wurde, selbst wenn die systemeigenen Daten im Dokument nicht geändert wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CONTAINER](../../visual-cpp-samples.md)   
 [MFC-Beispiel MFCBIND](../../visual-cpp-samples.md)   
 [CDocument-Klasse](../../mfc/reference/cdocument-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




