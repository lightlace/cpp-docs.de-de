---
title: CPropertyPage-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6a5b0e031aebb658b4da20d3aa9a6dd47f8c2a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851560"
---
# <a name="cpropertypage-class"></a>CPropertyPage-Klasse
Stellt die einzelnen Seiten eines Eigenschaftenblatts dar; wird auch als "Dialogfeld im Registerformat" bezeichnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|Erstellt ein `CPropertyPage`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|Ändert die Schaltfläche "OK", zum Lesen von schließen und die Schaltfläche "Abbrechen" nach einer nicht behebbaren Änderung auf der Seite ein modales Eigenschaftsblatt deaktiviert.|  
|[CPropertyPage::Construct](#construct)|Erstellt ein `CPropertyPage`-Objekt. Verwendung `Construct` , wenn Sie die Parameter zur Laufzeit angeben möchten oder bei Verwendung von Arrays.|  
|[CPropertyPage::GetPSP](#getpsp)|Ruft ab, die Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur zugeordnet ist die `CPropertyPage` Objekt.|  
|[CPropertyPage::OnApply](#onapply)|Wird vom Framework aufgerufen, wenn auf die Schaltfläche "jetzt übernehmen" geklickt wird.|  
|[CPropertyPage::OnCancel](#oncancel)|Wird vom Framework aufgerufen, wenn auf die Schaltfläche "Abbrechen" geklickt wird.|  
|[CPropertyPage:: OnKillActive](#onkillactive)|Wird von Framework aufgerufen, wenn die aktuelle Seite nicht mehr zur aktiven Seite wird. Führen Sie die datenvalidierung hier ein.|  
|[CPropertyPage::OnOK](#onok)|Vom Framework aufgerufen, wenn die OK, jetzt übernehmen oder Schaltfläche "Schließen" geklickt wird.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Wird vom Framework aufgerufen, wenn auf die Schaltfläche "Abbrechen" geklickt wird, und bevor der Abbruchvorgang stattgefunden hat.|  
|[CPropertyPage::OnReset](#onreset)|Wird vom Framework aufgerufen, wenn auf die Schaltfläche "Abbrechen" geklickt wird.|  
|[CPropertyPage::OnSetActive](#onsetactive)|Vom Framework aufgerufen, wenn die Seite zur aktiven Seite gemacht wird.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Vom Framework aufgerufen, wenn die zurück-Taste während einer Benutzens eines assistentartigen Eigenschaftsblatts geklickt wird.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Wird vom Framework aufgerufen, wenn auf die Schaltfläche "Fertig stellen" während einer Benutzens eines assistentartigen Eigenschaftsblatts geklickt wird.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Vom Framework aufgerufen, wenn auf die Schaltfläche "Weiter" während einer Benutzens eines assistentartigen Eigenschaftsblatts geklickt wird.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|Leitet die Nachricht für jede Seite des Eigenschaftenblatts an.|  
|[CPropertyPage::SetModified](#setmodified)|Rufen Sie zum Aktivieren oder deaktivieren die Schaltfläche "jetzt übernehmen".|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Die Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur. Bietet Zugriff auf grundlegende Eigenschaft Seitenparameter.|  
  
## <a name="remarks"></a>Hinweise  
 Wie Sie mit der Standarddialogfelder, Ableiten einer Klasse von `CPropertyPage` für jede Seite in Ihrem Eigenschaftenblatt. Mit `CPropertyPage`-abgeleitete Objekte, erstellen Sie zunächst eine [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) Objekt aus, und erstellen Sie ein Objekt für jede Seite, die im Eigenschaftenblatt gesendet wird. Rufen Sie [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) für jede Seite in der Tabelle, und klicken Sie dann das Eigenschaftenfenster anzuzeigen, durch den Aufruf [CPropertySheet:: DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) für ein modales Eigenschaftsblatt, oder [CPropertySheet:: Erstellen Sie](../../mfc/reference/cpropertysheet-class.md#create) für eines nicht modalen Eigenschaftenblatts.  
  
 Sie können einen Typ von Tab-Dialogfeld wird aufgerufen, einen Assistenten, der besteht aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten, die den Benutzer durch die Schritte eines Vorgangs, wie das Einrichten eines Geräts oder einen Newsletter erstellen. In einem Dialogfeld des Benutzens eines assistentartigen-Registerkarte die Eigenschaftenseiten müssen sich nicht auf die Registerkarten, und nur eine Eigenschaftenseite wird zu einem Zeitpunkt angezeigt. Anstatt die Schaltflächen "OK" und "jetzt übernehmen", hat auch ein Dialogfeld im Registerformat des Benutzens eines assistentartigen eine zurück-Schaltfläche eine Schaltfläche "Weiter" oder "Fertig stellen und Schaltfläche" Abbrechen ".  
  
 Weitere Informationen zum Einrichten eines Eigenschaftenblatts wie ein Assistent, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Weitere Informationen zur Verwendung von `CPropertyPage` Objekte finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose  
 Rufen Sie diese Funktion aus, nachdem auf die Daten auf einer Datenseite ein modales Eigenschaftsblatt eine nicht behebbare Änderung vorgenommen wurde.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird ändern die Schaltfläche "OK" zu schließen, und deaktivieren Sie die Schaltfläche "Abbrechen". Dies ändern, Warnungen, die der Benutzer, dass eine Änderung Permanent und die Änderungen werden nicht abgebrochen werden kann.  
  
 Die `CancelToClose` Memberfunktion ist "nothing" in einem nicht modalen Eigenschaftenblatts, da ein nicht modalen Eigenschaftenblatts keine Abbrechen-Schaltfläche in der Standardeinstellung verfügt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::QuerySiblings](#querysiblings).  
  
##  <a name="construct"></a>  CPropertyPage::Construct  
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
 *nIDTemplate*  
 Die ID der Vorlage für diese Seite verwendet.  
  
 *nIDCaption*  
 Die ID des Namens auf der Registerkarte für diese Seite platziert werden. Wenn der Wert 0 ist, wird der Name aus der Dialogfeldvorlage für diese Seite übernommen.  
  
 *lpszTemplateName*  
 Enthält eine Null-terminierte Zeichenfolge, die der Name einer Ressource ist.  
  
 *nIDHeaderTitle*  
 Die ID des Namens, der in die Position des Titels des Seitenkopfs Eigenschaft platziert werden. Standardmäßig ist 0.  
  
 *nIDHeaderSubTitle*  
 Die ID des Namens der Untertitel-Speicherort des Seitenkopfs Eigenschaft platziert werden. Standardmäßig ist 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird angezeigt, nachdem alle der folgenden Bedingungen erfüllt sind:  
  
-   Die Seite wurde auf eine Eigenschaft mit [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Des Eigenschaftenblattes [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../../mfc/reference/cpropertysheet-class.md#create) Funktion aufgerufen wurde.  
  
-   Der Benutzer ausgewählt hat (um Registerkarten) auf dieser Seite.  
  
 Rufen Sie `Construct` , wenn eine der anderen Klassenkonstruktoren nicht aufgerufen wurde. Die `Construct` Memberfunktion ist flexibel, da Sie die Anweisung Parameter leer lassen und dann mehrere Parameter und Konstruktion zu einem beliebigen Zeitpunkt im Code angeben können.  
  
 Verwenden Sie `Construct` Wenn Sie arbeiten mit Arrays, und rufen Sie `Construct` für jedes Element des Arrays, damit die Datenmember die richtigen Werte zugewiesen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage  
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
 *nIDTemplate*  
 Die ID der Vorlage für diese Seite verwendet.  
  
 *nIDCaption*  
 Die ID des Namens auf der Registerkarte für diese Seite platziert werden. Wenn der Wert 0 ist, wird der Name aus der Dialogfeldvorlage für diese Seite übernommen.  
  
 *dwSize*  
 *lpszTemplateName*  
 Verweist auf eine Zeichenfolge, die den Namen der Vorlage für diese Seite enthält. Darf nicht NULL sein.  
  
 *nIDHeaderTitle*  
 Die ID des Namens, der in die Position des Titels des Seitenkopfs Eigenschaft platziert werden.  
  
 *nIDHeaderSubTitle*  
 Die ID des Namens der Untertitel-Speicherort des Seitenkopfs Eigenschaft platziert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird angezeigt, nachdem alle der folgenden Bedingungen erfüllt sind:  
  
-   Die Seite wurde auf eine Eigenschaft mit [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Des Eigenschaftenblattes [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../../mfc/reference/cpropertysheet-class.md#create) Funktion aufgerufen wurde.  
  
-   Der Benutzer ausgewählt hat (um Registerkarten) auf dieser Seite.  
  
 Wenn Sie über mehrere Parameter (z. B., wenn Sie ein Array verwenden) verfügen, verwenden Sie [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) anstelle von `CPropertyPage`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>  CPropertyPage::GetPSP  
 Ruft ab, die Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur zugeordnet ist die `CPropertyPage` Objekt.  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die `PROPSHEETPAGE` Struktur.  
  
##  <a name="m_psp"></a>  CPropertyPage::m_psp  
 `m_psp` ist eine Struktur, deren Mitglieder, die Merkmale des speichern [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548).  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaftenseite zu initialisieren, sobald es erstellt wurde.  
  
 Weitere Informationen zu dieser Struktur, einschließlich einer Liste der Member, finden Sie unter `PROPSHEETPAGE` im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>  CPropertyPage::OnApply  
 Diese Memberfunktion wird von Framework aufgerufen, wenn der Benutzer auf OK oder die Schaltfläche "jetzt übernehmen" auswählt.  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Änderungen akzeptiert werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufrufen dieser Funktion durch das Framework auf allen Eigenschaftenseiten im Eigenschaftenblatt vorgenommenen Änderungen werden akzeptiert, das Eigenschaftenblatt behält den Fokus, und `OnApply` gibt "true" (der Wert 1). Vor dem `OnApply` kann aufgerufen werden, durch das Framework Sie aufgerufen hat, [SetModified](#setmodified) und als Parameter auf "true" festgelegt. Dadurch wird die Schaltfläche "jetzt übernehmen" aktiviert, sobald der Benutzer eine Änderung auf der Eigenschaftenseite vornimmt.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, klickt der Benutzer die Schaltfläche "jetzt übernehmen". Wenn Sie überschreiben, sollte die Funktion "true", um Änderungen zu übernehmen und "false", um zu verhindern, dass die Änderungen wirksam zurück.  
  
 Die standardmäßige Implementierung des `OnApply` Aufrufe `OnOK`.  
  
 Weitere Informationen zu den benachrichtigungsmeldungen gesendet werden, wenn der Benutzer in einem Eigenschaftenblatt die jetzt übernehmen oder Schaltfläche "OK" drückt, finden Sie unter [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnOK](#onok).  
  
##  <a name="oncancel"></a>  CPropertyPage::OnCancel  
 Diese Memberfunktion wird von Framework aufgerufen, wenn die Schaltfläche "Abbrechen" aktiviert ist.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Abbrechen-Schaltflächenaktionen ausführen. Der Standardwert wird verhindert, alle Änderungen, die vorgenommen wurden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>  CPropertyPage:: OnKillActive  
 Diese Memberfunktion wird von Framework aufgerufen, wenn die Seite nicht mehr zur aktiven Seite wird.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Daten erfolgreich aktualisiert wurden andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Durchführen von Aufgaben für spezielle-Überprüfung.  
  
 Die Standardimplementierung von dieser Memberfunktion kopiert die Einstellungen aus den Steuerelementen auf der Eigenschaftenseite auf die Membervariablen der Eigenschaftenseite. Wenn die Daten aufgrund eines Dialogfeld-Datenvalidierungsfehlers (DDV) nicht erfolgreich aktualisiert wurde, behält die Seite den Fokus.  
  
 Nachdem Sie diese Memberfunktion erfolgreich zurückgegeben wird, ruft das Framework der Seite [OnOK](#onok) Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>  CPropertyPage::OnOK  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn der Benutzer entweder "OK" oder "die Schaltfläche" jetzt übernehmen ", unmittelbar auf das Framework ruft auswählt [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer entweder "OK" oder "die Schaltfläche" jetzt übernehmen "auswählt, erhält das Framework die [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Benachrichtigung auf der Eigenschaftenseite. Der Aufruf von `OnOK` wird nicht hergestellt werden, wenn Sie aufrufen [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) , da die Eigenschaftenseite die Benachrichtigung nicht in diesem Fall sendet.  
  
 Überschreiben Sie diese Memberfunktion, um zusätzlich zur aktiven Seite spezifische Verhalten zu implementieren, wenn der Benutzer das gesamte Eigenschaftenblatt schließt.  
  
 Die Standardimplementierung von dieser Memberfunktion markiert die Seite "bereinigen", um darauf hinzuweisen, dass die Daten, in aktualisiert wurden der `OnKillActive` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel  
 Diese Memberfunktion wird von Framework aufgerufen, wenn der Benutzer klickt auf die Schaltfläche "Abbrechen", und bevor der Abbruchvorgang Aktion stattgefunden hat.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "false", um zu verhindern, dass den Vorgang "Abbrechen" oder "true", um es zu ermöglichen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion angeben, die das Programm akzeptiert, wenn der Benutzer die Schaltfläche "Abbrechen" klickt.  
  
 Die standardmäßige Implementierung des `OnQueryCancel` gibt TRUE zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>  CPropertyPage::OnReset  
 Diese Memberfunktion wird von Framework aufgerufen, wenn es sich bei der Betätigung der Schaltfläche "Abbrechen".  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufrufen dieser Funktion durch das Framework alle Eigenschaftenseiten, die von der Benutzer zuvor die Schaltfläche "jetzt übernehmen" vorgenommene Änderungen werden verworfen, und das Eigenschaftenblatt behält den Fokus.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, wenn der Benutzer die Schaltfläche "Abbrechen" klickt.  
  
 Die standardmäßige Implementierung des `OnReset` hat keine Auswirkungen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive  
 Diese Memberfunktion wird von Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und wird zur aktiven Seite.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Seite aktive erfolgreich festgelegt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Aufgaben auszuführen, wenn eine Seite aktiviert ist. Der Außerkraftsetzung von dieser Memberfunktion würde die Standardversion in der Regel rufen Sie nach der Aktualisierung der Datenmember, damit sie die Steuerelemente der Seite mit den neuen Daten aktualisieren kann.  
  
 Die Standardimplementierung erstellt das Fenster für die Seite, wenn nicht zuvor erstellt haben und macht es zur aktive Seite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack  
 Diese Memberfunktion wird von Framework aufgerufen, klickt der Benutzer auf die zurück-Taste in einem Assistenten.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Rückgabewert  
 0, automatisch zur nächsten Seite fortgefahren werden soll; 1, um zu verhindern, dass die Seite ändern. Geben Sie zum Springen zu einer Seite als der nächste den Bezeichner des Dialogfelds anzuzeigende zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die zurück-Taste gedrückt wird.  
  
 Weitere Informationen dazu, wie ein Eigenschaftenblatt des Benutzens eines assistentartigen vornehmen, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish  
 Diese Memberfunktion wird von Framework aufgerufen, klickt der Benutzer auf die Schaltfläche "Fertig stellen" des Assistenten.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Eigenschaftenblatt zerstört wird, wenn der Assistent abgeschlossen ist; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer klickt der **Fertig stellen** Schaltfläche in einem Assistenten, die das Framework ruft diese Funktion auf, wenn `OnWizardFinish` gibt "true" (einen Wert ungleich null), das Eigenschaftenblatt zerstört werden kann (aber nicht tatsächlich zerstört wird). Rufen Sie `DestroyWindow` das Eigenschaftenblatt zu zerstören. Rufen Sie keine `DestroyWindow` aus `OnWizardFinish`; zu Heaps auf Beschädigungen oder anderen Fehlern.  
  
 Sie können diese Member-Funktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die Schaltfläche "Fertig stellen" gedrückt wird, überschreiben. Wenn Sie diese Funktion zu überschreiben, geben Sie "false", um zu verhindern, dass das Eigenschaftenblatt zerstört zurück.  
  
 Weitere Informationen zu den benachrichtigungsmeldungen gesendet werden, wenn der Benutzer die Schaltfläche "Fertig stellen" in einem Eigenschaftenblatt Assistenten drückt, finden Sie unter [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) im Windows SDK.  
  
 Weitere Informationen dazu, wie ein Eigenschaftenblatt des Benutzens eines assistentartigen vornehmen, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext  
 Diese Memberfunktion wird von Framework aufgerufen, klickt der Benutzer auf "Weiter" des Assistenten.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Rückgabewert  
 0, automatisch zur nächsten Seite fortgefahren werden soll; 1, um zu verhindern, dass die Seite ändern. Geben Sie zum Springen zu einer Seite als der nächste den Bezeichner des Dialogfelds anzuzeigende zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die Schaltfläche "Weiter" gedrückt wird.  
  
 Weitere Informationen dazu, wie ein Eigenschaftenblatt des Benutzens eines assistentartigen vornehmen, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings  
 Rufen Sie diese Memberfunktion zum Weiterleiten einer Nachricht für jede Seite im Eigenschaftenblatt.  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 *wParam-Parameter*  
 Gibt zusätzliche Nachricht abhängige Informationen.  
  
 *lParam*  
 Gibt zusätzliche Nachricht abhängiges-Informationen  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ungleich NULL von einer Seite auf dem Eigenschaftenblatt oder 0, wenn alle Seiten den Wert 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Seite einen Wert ungleich NULL zurückgibt, sendet das Eigenschaftenblatt die Nachricht keine nachfolgenden Seiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>  CPropertyPage::SetModified  
 Rufen Sie diese Memberfunktion zum Aktivieren oder deaktivieren die Schaltfläche Jetzt übernehmen, basierend auf der gibt an, ob die Einstellungen auf der Eigenschaftenseite auf die entsprechenden externen Objekt angewendet werden soll.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bChanged*  
 TRUE gibt an, dass die Einstellungen für die Eigenschaftenseiten seit dem letzten geändert wurden, die sie angewendet wurden. "False", um anzugeben, dass die Einstellungen für die Eigenschaftenseiten angewendet wurden, oder ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verfolgt, Nachverfolgen der Seiten sind "geändert", d. h., für die Sie aufgerufen haben, Eigenschaftenseiten `SetModified( TRUE )`. Die Schaltfläche "jetzt übernehmen" wird immer aktiviert, wenn Sie aufrufen `SetModified( TRUE )` für eine der Seiten. Die Schaltfläche "jetzt übernehmen" deaktiviert wird, wenn Sie aufrufen `SetModified( FALSE )` für eine der Seiten, aber nur, wenn keiner der anderen Seiten "geändert" wurden ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)   
 [MFC-Beispiel SNAPVW](../../visual-cpp-samples.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropertySheet-Klasse](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
