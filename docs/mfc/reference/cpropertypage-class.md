---
title: CPropertyPage-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
dev_langs:
- C++
helpviewer_keywords:
- property pages, CPropertyPage class
- dialog boxes, tabs
- CPropertyPage class
- tab dialog boxes
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
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
ms.openlocfilehash: 13fb9befb6d1549493afa6cbed53ec4d41443c3a
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertypage-class"></a>CPropertyPage-Klasse
Stellt die einzelnen Seiten eines Eigenschaftenblatts dar; wird auch als "Dialogfeld im Registerformat" bezeichnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|Erstellt ein `CPropertyPage`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|Ändert die Schaltfläche "OK", um schließen zu lesen und die Schaltfläche "Abbrechen" nach einer nicht behebbaren Änderung auf der Seite eines modalen Eigenschaftenblatts deaktiviert.|  
|[CPropertyPage::Construct](#construct)|Erstellt ein `CPropertyPage`-Objekt. Verwendung `Construct` Wenn Sie die Parameter zur Laufzeit angeben möchten oder wenn Sie Arrays verwenden.|  
|[CPropertyPage::GetPSP](#getpsp)|Ruft den Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur zugeordnet ist die `CPropertyPage` Objekt.|  
|[CPropertyPage::OnApply](#onapply)|Wird vom Framework aufgerufen, wenn die übernehmen-Schaltfläche geklickt wird.|  
|[CPropertyPage::OnCancel](#oncancel)|Wird vom Framework aufgerufen, wenn die Schaltfläche Abbrechen geklickt wird.|  
|[CPropertyPage:: OnKillActive](#onkillactive)|Wird vom Framework aufgerufen, wenn die aktuelle Seite nicht mehr die aktive Seite ist. Führen Sie die Validierung hier.|  
|[CPropertyPage::OnOK](#onok)|Wird vom Framework aufgerufen, wenn die OK, jetzt anwenden oder Schaltfläche "Schließen" geklickt wird.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Vom Framework aufgerufen, wenn die Schaltfläche Abbrechen geklickt wird, und bevor der Abbruchvorgang stattgefunden hat.|  
|[CPropertyPage::OnReset](#onreset)|Wird vom Framework aufgerufen, wenn die Schaltfläche Abbrechen geklickt wird.|  
|[CPropertyPage::OnSetActive](#onsetactive)|Vom Framework aufgerufen, wenn die Seite die aktive Seite erfolgt.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Wird vom Framework aufgerufen, wenn die zurück-Schaltfläche, beim Verwenden des Eigenschaftenfensters Assistent-Typ geklickt wird.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Vom Framework aufgerufen, wenn auf die Schaltfläche Fertig stellen geklickt wird, beim Verwenden des Eigenschaftenfensters Assistent-Typ.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Wird vom Framework aufgerufen, wenn die Schaltfläche "Weiter", beim Verwenden des Eigenschaftenfensters Assistent-Typ geklickt wird.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|Leitet die Nachricht auf jeder Seite der Eigenschaftenseite.|  
|[CPropertyPage::SetModified](#setmodified)|So aktivieren oder deaktivieren die Schaltfläche "jetzt" aufrufen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur. Bietet Zugriff auf grundlegende Eigenschaft Seitenparameter.|  
  
## <a name="remarks"></a>Hinweise  
 Wie mit standard-Dialogfeldern einer Klasse von ableiten `CPropertyPage` für jede Seite in Ihrem Eigenschaftsblatt. Verwenden `CPropertyPage`-abgeleitete Objekte zuerst erstellen eine [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) -Objekt, und erstellen Sie ein Objekt für jede Seite, die im Eigenschaftenblatt wechselt. Rufen Sie [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) für jede Seite in der Tabelle, und zeigen Sie das Eigenschaftenfenster durch Aufrufen von [CPropertySheet:: DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) für ein modales Eigenschaftenblatt oder [CPropertySheet::Create](../../mfc/reference/cpropertysheet-class.md#create) für ein nicht modales Eigenschaftenblatt.  
  
 Sie können ein Dialogfeld im Registerformat bezeichnet einen Assistenten, besteht aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten, die den Benutzer durch die Schritte eines Vorgangs, z. B. ein Gerät einrichten oder Erstellen eines Magazins erstellen. Eine Assistententyp Registerkarte im Dialogfeld Eigenschaftenseiten keine Registerkarten, und nur eine Eigenschaftenseite zu einem Zeitpunkt sichtbar ist. Anstatt die Schaltflächen OK und jetzt enthält außerdem ein Assistenten-Registerkarte eine zurück-Schaltfläche eine Schaltfläche Weiter oder Fertig stellen und eine Schaltfläche Abbrechen.  
  
 Weitere Informationen zum Einrichten einer Eigenschaftenblätter als Assistenten finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Weitere Informationen zur Verwendung von `CPropertyPage` Objekte finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>CPropertyPage::CancelToClose  
 Rufen Sie diese Funktion aus, nachdem die Daten in eine Seite mit einem modalen Eigenschaftenblatt eine nicht behebbare Änderung vorgenommen wurde.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird ändern die Schaltfläche "OK" zu schließen, und deaktivieren Sie die Schaltfläche "Abbrechen". So ändern Sie Warnungen, die der Benutzer, dass eine Änderung dauerhaft und die Änderungen rückgängig gemacht werden kann.  
  
 Die `CancelToClose` Memberfunktion "nothing" in einem nicht modalen Eigenschaftenblatts, da kein nicht modalen Eigenschaftenblatts keine Schaltfläche zum Abbrechen in der Standardeinstellung verfügt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::QuerySiblings](#querysiblings).  
  
##  <a name="construct"></a>CPropertyPage::Construct  
 Rufen Sie diese Memberfunktion zum Erstellen einer `CPropertyPage` Objekt.  
  
```  
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0);

 
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDTemplate`  
 Die ID der Vorlage für diese Seite verwendet.  
  
 `nIDCaption`  
 ID des Namens auf der Registerkarte für diese Seite platziert werden. Bei 0 wird der Name aus der Dialogfeldvorlage für diese Seite übernommen werden.  
  
 `lpszTemplateName`  
 Enthält eine auf Null endende Zeichenfolge, die den Namen der Dialogfeldvorlagen-Ressource ist.  
  
 `nIDHeaderTitle`  
 ID des Namens in die Position des Titels des Seitenkopfs-Eigenschaft platziert werden. Standardmäßig ist 0.  
  
 `nIDHeaderSubTitle`  
 ID des Namens im Verzeichnis Untertitel die Kopfzeile der Seite platziert werden. Standardmäßig ist 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird angezeigt, nachdem alle der folgenden Umstände zutreffen:  
  
-   Die Seite wurde zu einer Eigenschaft mithilfe [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Des Eigenschaftenblattes [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../../mfc/reference/cpropertysheet-class.md#create) Funktion aufgerufen wurde.  
  
-   Der Benutzer ausgewählt hat (um Registerkarten) auf dieser Seite.  
  
 Rufen Sie **erstellen** , wenn die andere Klasse Konstruktoren nicht aufgerufen wurde. Die `Construct` Memberfunktion ist flexibel, da Sie die Anweisung Parameter leer lassen und dann mehrere Parameter und Erstellung an einem beliebigen Punkt im Code angeben können.  
  
 Verwenden Sie `Construct` Wenn Sie arbeiten mit Arrays und müssen Sie aufrufen, **erstellen** für jedes Element des Arrays, damit die Datenmember richtige Werte zugewiesen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#112;](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>CPropertyPage::CPropertyPage  
 Erstellt ein `CPropertyPage`-Objekt.  
  
```  
CPropertyPage();

 
explicit CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
explicit CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```  
  
### <a name="parameters"></a>Parameter  
 `nIDTemplate`  
 Die ID der Vorlage für diese Seite verwendet.  
  
 `nIDCaption`  
 ID des Namens auf der Registerkarte für diese Seite platziert werden. Bei 0 wird der Name aus der Dialogfeldvorlage für diese Seite übernommen werden.  
  
 `dwSize`  
 `lpszTemplateName`  
 Zeigt auf eine Zeichenfolge, die den Namen der Vorlage für diese Seite enthält. Nicht **NULL**.  
  
 `nIDHeaderTitle`  
 ID des Namens in die Position des Titels des Seitenkopfs-Eigenschaft platziert werden.  
  
 `nIDHeaderSubTitle`  
 ID des Namens im Verzeichnis Untertitel die Kopfzeile der Seite platziert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird angezeigt, nachdem alle der folgenden Umstände zutreffen:  
  
-   Die Seite wurde zu einer Eigenschaft mithilfe [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Des Eigenschaftenblattes [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../../mfc/reference/cpropertysheet-class.md#create) Funktion aufgerufen wurde.  
  
-   Der Benutzer ausgewählt hat (um Registerkarten) auf dieser Seite.  
  
 Wenn Sie mehrere Parameter (z. B., wenn Sie ein Array verwenden), verwenden [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) anstelle von `CPropertyPage`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#113;](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>CPropertyPage::GetPSP  
 Ruft den Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur zugeordnet ist die `CPropertyPage` Objekt.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die **PROPSHEETPAGE** Struktur.  
  
##  <a name="m_psp"></a>CPropertyPage::m_psp  
 `m_psp`ist eine Struktur, deren Mitglieder die Merkmale des speichern [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaftenseite zu initialisieren, sobald es erstellt wurde.  
  
 Weitere Informationen zu dieser Struktur, die eine Auflistung von Membern, einschließlich finden Sie unter **PROPSHEETPAGE** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#128;](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>CPropertyPage::OnApply  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn der Betätigung OK oder auf die Schaltfläche jetzt anwenden.  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderungen akzeptiert werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Framework diese Funktion aufruft, Änderungen auf alle Eigenschaftenseiten im Eigenschaftenblatt akzeptiert werden, das Eigenschaftenblatt behält den Fokus, und `OnApply` gibt **TRUE** (der Wert 1). Vor dem `OnApply` kann aufgerufen werden, durch das Framework Sie aufgerufen hat, [SetModified](#setmodified) und legen Sie den Parameter auf **TRUE**. Dies aktiviert die Schaltfläche jetzt anwenden, sobald der Benutzer eine Änderung auf der Eigenschaftenseite vornimmt.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm gibt, klickt der Benutzer auf die Schaltfläche jetzt anwenden. Beim Überschreiben von die Funktion zurückgeben sollte **TRUE** um Änderungen zu übernehmen und **FALSE** verhindern, dass die Änderungen wirksam.  
  
 Die standardmäßige Implementierung des `OnApply` Aufrufe `OnOK`.  
  
 Weitere Informationen zu der Benachrichtigung gesendet, wenn der Benutzer in einem Eigenschaftenblatt die jetzt anwenden oder OK-Schaltfläche drückt, finden Sie unter [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnOK](#onok).  
  
##  <a name="oncancel"></a>CPropertyPage::OnCancel  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn die Schaltfläche "Abbrechen" aktiviert ist.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Abbrechen Aktionen ausführen. Standardmäßig wird die vorgenommenen Änderungen negiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#114;](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>CPropertyPage:: OnKillActive  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn die Seite nicht mehr die aktive Seite ist.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Daten aktualisiert wurde, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion Objektdaten Validierung Aufgaben.  
  
 Die standardmäßige Implementierung von dieser Memberfunktion kopiert die Einstellungen aus den Steuerelementen auf der Eigenschaftenseite auf der Eigenschaftenseite die Membervariablen. Wenn die Daten aufgrund eines Fehlers Dialogfeld Überprüfung (DDV) nicht erfolgreich aktualisiert wurde, behält die Seite den Fokus.  
  
 Nachdem diese Memberfunktion erfolgreich zurückgegeben wird, ruft das Framework der Seite [OnOK](#onok) Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#115;](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>CPropertyPage::OnOK  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer entweder auf OK oder auf die Schaltfläche jetzt unmittelbar auf das Framework ruft [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer entweder auf OK oder auf die Schaltfläche "Übernehmen" entscheidet, empfängt das Framework die [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Benachrichtigung auf der Eigenschaftenseite. Der Aufruf von `OnOK` wird nicht vorgenommen werden, wenn Sie aufrufen [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) , da die Eigenschaftenseite in diesem Fall keine Benachrichtigung gesendet werden.  
  
 Überschreiben Sie diese Memberfunktion zum zusätzlich die aktuell aktive Seite spezifische Verhalten zu implementieren, wenn der Benutzer das gesamte Eigenschaftenblatt schließt.  
  
 Die standardmäßige Implementierung von dieser Memberfunktion kennzeichnet die Seite als "bereinigen", um anzugeben, dass die Aktualisierung der Daten in der `OnKillActive` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView Nr.&116;](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>CPropertyPage::OnQueryCancel  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn der Benutzer auf die Schaltfläche "Abbrechen" klickt, und bevor der Abbruchvorgang Aktion stattgefunden hat.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **FALSE** verhindert, dass der Vorgang "Abbrechen" oder "true", um es zu ermöglichen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die das Programm akzeptiert, wenn der Benutzer die Schaltfläche "Abbrechen" klickt.  
  
 Die standardmäßige Implementierung des `OnQueryCancel` gibt **TRUE**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#117;](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>CPropertyPage::OnReset  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn die Betätigung der Schaltfläche "Abbrechen".  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Framework diese Funktion aufruft, Änderungen an alle Eigenschaftenseiten, die vom Benutzer zuvor die Schaltfläche Jetzt übernehmen auswählen vorgenommen wurden, werden verworfen und Eigenschaftenblatt behält den Fokus.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, wenn der Benutzer die Schaltfläche "Abbrechen" klickt.  
  
 Die standardmäßige Implementierung des `OnReset` wird keine Aktion ausgeführt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="onsetactive"></a>CPropertyPage::OnSetActive  
 Diese Member-Funktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt und wird die aktive Seite.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Seite erfolgreich aktiviert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Aufgaben auszuführen, wenn eine Seite aktiviert wird. Die Überschreibung von dieser Memberfunktion würde in der Regel die Standardversion aufrufen, nach der Aktualisierung auf Datenmember, so, dass die Steuerelemente mit den neuen Daten aktualisieren können.  
  
 Die standardmäßige Implementierung erstellt das Fenster für die Seite Wenn nicht zuvor erstellt haben und erleichtert die aktive Seite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="onwizardback"></a>CPropertyPage::OnWizardBack  
 Diese Memberfunktion wird vom Framework aufgerufen, klickt der Benutzer auf die Schaltfläche zurück in einen Assistenten.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Rückgabewert  
 0, um automatisch zur nächsten Seite zu gelangen;&1;, um zu verhindern, dass die Seite ändern. Geben Sie zum Anzeigen einer Seite nicht die nächste zurück des Bezeichners des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die zurück-Taste gedrückt wird.  
  
 Weitere Informationen zu einem Eigenschaftenblatt Assistent-Typ, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#118;](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>CPropertyPage::OnWizardFinish  
 Diese Memberfunktion wird vom Framework aufgerufen, klickt der Benutzer auf die Schaltfläche "Fertig stellen" im Assistenten.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenfenster zerstört wird, wenn der Assistent abgeschlossen ist; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer klickt der **Fertig stellen** Schaltfläche in einem Assistenten wird das Framework ruft diese Funktion auf, wenn `OnWizardFinish` gibt **TRUE** (einen Wert ungleich null), das Eigenschaftenfenster zerstört werden kann (aber nicht tatsächlich zerstört). Rufen Sie `DestroyWindow` Eigenschaftenblatt zu zerstören. Rufen Sie `DestroyWindow` aus `OnWizardFinish`; zu einer Heap-Beschädigung oder andere Fehler.  
  
 Sie können diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die Schaltfläche Fertig stellen geklickt wird, überschreiben. Beim Überschreiben dieser Funktion zurückgeben **FALSE** verhindern, dass das Eigenschaftenblatt zerstört wird.  
  
 Weitere Informationen zu der Benachrichtigung gesendet, wenn der Benutzer die Schaltfläche Fertig stellen in einem Eigenschaftenblatt Assistenten drückt, finden Sie unter [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu einem Eigenschaftenblatt Assistent-Typ, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#119;](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#120;](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#121;](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#122;](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>CPropertyPage::OnWizardNext  
 Diese Memberfunktion wird vom Framework aufgerufen, klickt der Benutzer auf die Schaltfläche Weiter in einem Assistenten.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Rückgabewert  
 0, um automatisch zur nächsten Seite zu gelangen;&1;, um zu verhindern, dass die Seite ändern. Geben Sie zum Anzeigen einer Seite nicht die nächste zurück des Bezeichners des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die Schaltfläche weiter gedrückt wird.  
  
 Weitere Informationen zu einem Eigenschaftenblatt Assistent-Typ, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#123;](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>CPropertyPage::QuerySiblings  
 Rufen Sie diese Memberfunktion zum Weiterleiten einer Nachricht auf jeder Seite im Eigenschaftenblatt.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `wParam`  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 `lParam`  
 Gibt zusätzliche Nachricht abhängige Informationen  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ungleich NULL von einer Seite in das Eigenschaftenfenster oder 0, wenn alle Seiten einen Wert von 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Seite einen Wert ungleich NULL zurückgibt, sendet das Eigenschaftenblatt die Nachricht keine nachfolgenden Seiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#124;](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#125;](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#126;](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>CPropertyPage::SetModified  
 Rufen Sie diese Memberfunktion zum Aktivieren oder deaktivieren die Schaltfläche Jetzt übernehmen, basierend auf, ob die Einstellungen auf der Eigenschaftenseite auf die entsprechenden externen Objekt angewendet werden soll.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bChanged`  
 **TRUE** an, dass die Einstellungen für die Eigenschaft sie angewendet wurden, seit der letzten geändert wurden **FALSE** angeben, dass die Einstellungen für die Eigenschaft angewendet wurden oder ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework hält, Nachverfolgen der Seiten sind "fehlerhaft" anzeigt, d. h., die Eigenschaftenseiten für die Sie aufgerufen haben **SetModified (TRUE)**. Die Schaltfläche "jetzt" ist immer aktiviert, wenn Sie aufrufen **SetModified (TRUE)** für eine der Seiten. Die Schaltfläche jetzt deaktiviert sein, beim Aufruf von **SetModified (FALSE)** für eine der Seiten, aber nur, wenn ist keine der anderen Seiten "unsaubere".  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[127 NVC_MFCDocView](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)

