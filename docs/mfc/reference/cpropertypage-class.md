---
title: CPropertyPage-Klasse | Microsoft Docs
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: f14dfe29a6fa941192c2cfe792f16e4b032af941
ms.lasthandoff: 04/01/2017

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
|[CPropertyPage::CancelToClose](#canceltoclose)|Ändert die Schaltfläche "OK", um schließen zu lesen und die Schaltfläche "Abbrechen" nach einer Änderung eines nicht behebbaren auf der Seite eines modalen Eigenschaftenblatts deaktiviert.|  
|[CPropertyPage::Construct](#construct)|Erstellt ein `CPropertyPage`-Objekt. Verwendung `Construct` Wenn Sie die Parameter zur Laufzeit angeben möchten, oder bei Verwendung von Arrays.|  
|[CPropertyPage::GetPSP](#getpsp)|Ruft den Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) zugeordnete Struktur der `CPropertyPage` Objekt.|  
|[CPropertyPage::OnApply](#onapply)|Vom Framework aufgerufen, wenn auf die Schaltfläche "jetzt" geklickt wird.|  
|[CPropertyPage::OnCancel](#oncancel)|Vom Framework aufgerufen, wenn die Schaltfläche "Abbrechen" geklickt wird.|  
|[CPropertyPage:: OnKillActive](#onkillactive)|Vom Framework aufgerufen, wenn die aktuelle Seite nicht mehr die aktive Seite ist. Führen Sie hier die datenüberprüfung.|  
|[CPropertyPage::OnOK](#onok)|Vom Framework aufgerufen, wenn der OK jetzt anwenden bzw. Schaltfläche "Schließen" geklickt wird.|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|Vom Framework aufgerufen, wenn die Schaltfläche "Abbrechen" geklickt wird, und bevor der Abbruchvorgang stattgefunden hat.|  
|[CPropertyPage::OnReset](#onreset)|Vom Framework aufgerufen, wenn die Schaltfläche "Abbrechen" geklickt wird.|  
|[CPropertyPage::OnSetActive](#onsetactive)|Vom Framework aufgerufen, wenn die Seite die aktive Seite erfolgt.|  
|[CPropertyPage::OnWizardBack](#onwizardback)|Vom Framework aufgerufen, wenn auf die Schaltfläche "zurück" geklickt wird, bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|Vom Framework aufgerufen, wenn auf "Fertig stellen" geklickt wird, bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|Vom Framework aufgerufen, wenn die Schaltfläche "Weiter" geklickt wird, bei der Verwendung von Eigenschaftenblätter Assistenten-Typ.|  
|[CPropertyPage::QuerySiblings](#querysiblings)|Leitet die Nachricht auf jeder Seite des Eigenschaftsblatt weiter.|  
|[CPropertyPage::SetModified](#setmodified)|So aktivieren oder deaktivieren die Schaltfläche "jetzt" aufrufen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Die Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) Struktur. Bietet Zugriff auf grundlegende Eigenschaft Seitenparameter.|  
  
## <a name="remarks"></a>Hinweise  
 Als standard Dialogfelder, einer Klasse von ableiten `CPropertyPage` für jede Seite in Ihrem Eigenschaftsblatt. Verwenden `CPropertyPage`-abgeleitete Objekte, erstellen Sie zunächst eine [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) -Objekt, und erstellen Sie ein Objekt für jede Seite, die im Eigenschaftenblatt wechselt. Rufen Sie [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage) für jede Seite in der Tabelle und klicken Sie dann das Eigenschaftenfenster anzuzeigen, durch den Aufruf [CPropertySheet:: DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) für ein modales Eigenschaftenblatt oder [CPropertySheet::Create](../../mfc/reference/cpropertysheet-class.md#create) für eines nicht modalen Eigenschaftenblatts.  
  
 Sie können einen Typ von Tab-Dialogfeld wird aufgerufen, einen Assistenten, besteht aus einem Eigenschaftenblatt mit einer Sequenz von Eigenschaftenseiten, mit denen den Benutzer durch die Schritte eines Vorgangs, beispielsweise das Einrichten eines Geräts oder das Erstellen von eines Newsletters begleitet erstellen. In einem Dialogfeld des Assistenten-Registerkarte die Eigenschaftenseiten keine Registerkarten, und nur eine Eigenschaftenseite ist immer sichtbar. Außerdem muss ein Dialogfeld des Assistenten-Registerkarte anstatt Schaltflächen "OK" und "jetzt" eine Schaltfläche "zurück", eine Schaltfläche "Weiter" oder "Fertig stellen und eine Schaltfläche" Abbrechen ".  
  
 Weitere Informationen zum Einrichten von Eigenschaftenblätter als Assistenten finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode). Weitere Informationen zur Verwendung von `CPropertyPage` Objekte finden Sie im Artikel [Eigenschaftenblätter und Eigenschaftenseiten](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>CPropertyPage::CancelToClose  
 Mit dieser Funktion werden, nachdem die Daten in einer Seite eines modalen Eigenschaftenblatts eine nicht behebbare Änderung vorgenommen wurde.  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ändert die Schaltfläche "OK" zu schließen und deaktivieren Sie die Schaltfläche "Abbrechen". So ändern Sie Warnungen, die der Benutzer, dass eine Änderung dauerhaft und die Änderungen wird nicht abgebrochen werden kann.  
  
 Die `CancelToClose` Memberfunktion ist "nothing" in einem nicht modalen Eigenschaftenblatts, da ein nicht modalen Eigenschaftenblatts nicht über eine Schaltfläche "Abbrechen" in der Standardeinstellung verfügt.  
  
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
 ID der Vorlage, die für diese Seite verwendet.  
  
 `nIDCaption`  
 Die ID des Namens auf der Registerkarte für diese Seite platziert werden soll. Bei 0 werden der Name aus der Dialogfeldvorlage für diese Seite weitergeleitet.  
  
 `lpszTemplateName`  
 Enthält eine Null-terminierte Zeichenfolge, die den Namen der Dialogfeldvorlagen-Ressource ist.  
  
 `nIDHeaderTitle`  
 Die ID des Namens in die Position des Titels des Seitenkopfs Eigenschaft platziert werden soll. Standardmäßig 0.  
  
 `nIDHeaderSubTitle`  
 Die ID des Namens am Speicherort Untertitel des Seitenkopfs Eigenschaft platziert werden soll. Standardmäßig 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird angezeigt, nachdem alle der folgenden Bedingungen erfüllt sind:  
  
-   Die Seite wurde hinzugefügt, um eine Eigenschaft mit [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Des Eigenschaftenblattes [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../../mfc/reference/cpropertysheet-class.md#create) Funktion aufgerufen wurde.  
  
-   Der Benutzer hat ausgewählt (im Registerkartenformat zu) auf dieser Seite.  
  
 Rufen Sie **erstellen** wäre die andere Klasse Konstruktoren nicht aufgerufen worden. Die `Construct` Memberfunktion ist flexibel, da die Anweisung Parameter leer lassen, und klicken Sie dann mehrere Parameter und zur Erstellung an einem beliebigen Punkt im Code angeben.  
  
 Verwenden Sie `Construct` Wenn Sie arbeiten mit Arrays, und rufen Sie **erstellen** für jedes Element des Arrays, damit die Datenmember richtige Werte zugewiesen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
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
 ID der Vorlage, die für diese Seite verwendet.  
  
 `nIDCaption`  
 Die ID des Namens auf der Registerkarte für diese Seite platziert werden soll. Bei 0 werden der Name aus der Dialogfeldvorlage für diese Seite weitergeleitet.  
  
 `dwSize`  
 `lpszTemplateName`  
 Verweist auf eine Zeichenfolge, die den Namen der Vorlage für diese Seite enthält. Nicht mit **NULL**.  
  
 `nIDHeaderTitle`  
 Die ID des Namens in die Position des Titels des Seitenkopfs Eigenschaft platziert werden soll.  
  
 `nIDHeaderSubTitle`  
 Die ID des Namens am Speicherort Untertitel des Seitenkopfs Eigenschaft platziert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird angezeigt, nachdem alle der folgenden Bedingungen erfüllt sind:  
  
-   Die Seite wurde hinzugefügt, um eine Eigenschaft mit [CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage).  
  
-   Des Eigenschaftenblattes [DoModal](../../mfc/reference/cpropertysheet-class.md#domodal) oder [erstellen](../../mfc/reference/cpropertysheet-class.md#create) Funktion aufgerufen wurde.  
  
-   Der Benutzer hat ausgewählt (im Registerkartenformat zu) auf dieser Seite.  
  
 Wenn Sie mehrere Parameter (z. B., wenn Sie ein Array verwenden), verwenden [CPropertySheet::Construct](../../mfc/reference/cpropertysheet-class.md#construct) anstelle von `CPropertyPage`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>CPropertyPage::GetPSP  
 Ruft den Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) zugeordnete Struktur der `CPropertyPage` Objekt.  
  
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
 Verwenden Sie diese Struktur, um die Darstellung einer Eigenschaftenseite initialisiert werden, nachdem es erstellt wurde.  
  
 Weitere Informationen zu dieser Struktur, einschließlich einer Liste der Member, finden Sie unter **PROPSHEETPAGE** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>CPropertyPage::OnApply  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn der Benutzer auf OK oder die Schaltfläche "jetzt" auswählt.  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Änderungen zulässig sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Framework über diese Funktion aufruft, auf alle Eigenschaftenseiten im Eigenschaftenblatt vorgenommenen Änderungen werden akzeptiert, das Eigenschaftenblatt behält den Fokus, und `OnApply` gibt **"true"** (der Wert 1). Vor dem `OnApply` kann aufgerufen werden, durch das Framework Sie aufgerufen hat, [SetModified](#setmodified) und legen Sie die Parameter auf **"true"**. Dadurch wird die Schaltfläche "jetzt anwenden" aktiviert, als der Benutzer eine Änderung auf der Eigenschaftenseite vornimmt.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm hat, klickt der Benutzer die Schaltfläche "jetzt anwenden". Zum Überschreiben, sollte die Funktion zurückgeben **"true"** zum Übernehmen der Änderungen und **"false"** um zu verhindern, dass die Änderungen wirksam.  
  
 Die standardmäßige Implementierung des `OnApply` Aufrufe `OnOK`.  
  
 Weitere Informationen zu benachrichtigungsmeldungen gesendet, wenn der Benutzer die jetzt anwenden oder Schaltfläche "OK" in einem Eigenschaftenblatt drückt, finden Sie unter [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnOK](#onok).  
  
##  <a name="oncancel"></a>CPropertyPage::OnCancel  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn die Schaltfläche "Abbrechen" aktiviert ist.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Ausführen von Aktionen "Abbrechen". Die Standardeinstellung negiert Änderungen, die vorgenommen wurden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>CPropertyPage:: OnKillActive  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn die Seite nicht mehr die aktive Seite ist.  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Daten aktualisiert wurde, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um spezielle Data Validation Aufgaben auszuführen.  
  
 Die Standardimplementierung von dieser Memberfunktion kopiert Einstellungen von den Steuerelementen auf der Eigenschaftenseite auf die Membervariablen der Eigenschaftenseite. Wenn die Daten aufgrund eines Dialogfeld-Datenvalidierungsfehlers (DDV) nicht erfolgreich aktualisiert wurde, behält der Seite "den Fokus.  
  
 Nachdem diese Memberfunktion erfolgreich zurückgegeben hat, ruft das Framework der Seite [OnOK](#onok) Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>CPropertyPage::OnOK  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn der Benutzer entweder auf OK oder auf die Schaltfläche "jetzt anwenden", unmittelbar auf das Framework ruft auswählt [OnKillActive](#onkillactive).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer auf OK oder die Schaltfläche "jetzt" auswählt, erhält das Framework der [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Benachrichtigung auf der Eigenschaftenseite. Der Aufruf von `OnOK` wird nicht vorgenommen werden, wenn Sie aufrufen [CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton) , da die Eigenschaftsseite "in diesem Fall keine Benachrichtigung gesendet werden.  
  
 Überschreiben Sie diese Memberfunktion um zusätzlich die derzeit aktive Seite spezifische Verhalten zu implementieren, wenn Benutzer das gesamte Eigenschaftenblatt schließt.  
  
 Die Standardimplementierung von dieser Memberfunktion kennzeichnet die Seite als "bereinigen", um widerzuspiegeln, die Updates der Daten in der `OnKillActive` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>CPropertyPage::OnQueryCancel  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn der Benutzer klickt auf die Schaltfläche "Abbrechen", und bevor der Abbruchvorgang Aktion stattgefunden hat.  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"false"** verhindert, dass der Vorgang "Abbrechen" oder "true", um es zu ermöglichen.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, die das Programm benötigt, klickt der Benutzer die Schaltfläche "Abbrechen".  
  
 Die standardmäßige Implementierung des `OnQueryCancel` gibt **"true"**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>CPropertyPage::OnReset  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn die Betätigung der Schaltfläche "Abbrechen".  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufrufen dieser Funktion durch das Framework für alle Eigenschaftenseiten, die durch den Benutzer, die zuvor Auswählen der Schaltfläche "jetzt anwenden" vorgenommenen Änderungen werden verworfen, und das Eigenschaftenblatt behält den Fokus.  
  
 Überschreiben Sie diese Memberfunktion zum angeben, welche Aktion das Programm akzeptiert, klickt der Benutzer die Schaltfläche "Abbrechen".  
  
 Die standardmäßige Implementierung des `OnReset` wird keine Aktion ausgeführt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertyPage::OnCancel](#oncancel).  
  
##  <a name="onsetactive"></a>CPropertyPage::OnSetActive  
 Diese Memberfunktion wird vom Framework aufgerufen, wenn die Seite vom Benutzer ausgewählt wird und als aktive Seite.  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Seite active festgelegt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um Aufgaben auszuführen, wenn eine Seite aktiviert wird. Die Außerkraftsetzung von dieser Memberfunktion würde in der Regel die Standardversion aufrufen, nach der Aktualisierung der Datenmember so, dass die Steuerelemente der Seite mit den neuen Daten aktualisieren können.  
  
 Die standardmäßige Implementierung erstellt das Fenster für die Seite, wenn nicht zuvor erstellt haben und erleichtert die aktive Seite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext).  
  
##  <a name="onwizardback"></a>CPropertyPage::OnWizardBack  
 Diese Memberfunktion wird vom Framework aufgerufen, klickt der Benutzer auf die Schaltfläche "zurück" des Assistenten.  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>Rückgabewert  
 0 bis automatisch zur nächsten Seite zu gelangen; 1, um zu verhindern, dass die Seite ändern. Geben Sie zum Springen zu einer Seite als der nächste zurück den Bezeichner des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn die zurück-Taste gedrückt wird.  
  
 Weitere Informationen zum einen Assistenten-Typeigenschaft Arbeitsblatt zu machen, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>CPropertyPage::OnWizardFinish  
 Diese Memberfunktion wird vom Framework aufgerufen, der Benutzer klickt auf "Fertig stellen" des Assistenten.  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Eigenschaftenfenster zerstört wird, nach Abschluss des Assistenten; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer klickt auf die **Fertig stellen** Schaltfläche in einem Assistenten wird das Framework ruft diese Funktion; Wenn `OnWizardFinish` gibt **"true"** (ein Wert ungleich null), das Eigenschaftenblatt zerstört werden kann (aber nicht tatsächlich zerstört). Rufen Sie `DestroyWindow` Eigenschaftenblatt zu zerstören. Rufen Sie nicht `DestroyWindow` aus `OnWizardFinish`; dies daher führt dazu, dass Heapbeschädigung oder ein anderer Fehler.  
  
 Sie können diese Memberfunktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, beim Klicken auf "Fertig stellen" aufgerufen wird, überschreiben. Beim Überschreiben dieser Funktion zurückgeben **"false"** um zu verhindern, dass das Eigenschaftenblatt zerstört wird.  
  
 Weitere Informationen zu benachrichtigungsmeldungen gesendet, wenn der Benutzer in einem Eigenschaftenblatt Assistenten "Fertig stellen" drückt, finden Sie unter [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zum einen Assistenten-Typeigenschaft Arbeitsblatt zu machen, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>CPropertyPage::OnWizardNext  
 Diese Memberfunktion wird vom Framework aufgerufen, klickt der Benutzer auf die Schaltfläche "Weiter", in einem Assistenten.  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>Rückgabewert  
 0 bis automatisch zur nächsten Seite zu gelangen; 1, um zu verhindern, dass die Seite ändern. Geben Sie zum Springen zu einer Seite als der nächste zurück den Bezeichner des Dialogfelds angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion, um eine Aktion anzugeben, die der Benutzer ausführen muss, wenn, dass Sie die Schaltfläche "weiter gedrückt wird".  
  
 Weitere Informationen zum einen Assistenten-Typeigenschaft Arbeitsblatt zu machen, finden Sie unter [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
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
 Gibt zusätzliche Nachricht abhängiges-Informationen  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ungleich NULL aus einer Seite im Eigenschaftenblatt oder 0, wenn alle Seiten einen Wert von 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Seite einen Wert ungleich NULL zurückgibt, sendet Eigenschaftenblatt die Nachricht keine nachfolgenden Seiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView #124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>CPropertyPage::SetModified  
 Rufen Sie diese Memberfunktion zum Aktivieren oder deaktivieren die Schaltfläche Jetzt übernehmen, basierend auf, ob die Einstellungen auf der Eigenschaftenseite auf die entsprechenden externen Objekt angewendet werden soll.  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bChanged`  
 **"True"** , um anzugeben, dass die eigenschafteneinstellungen für die Seite sie angewendet wurden, seit der letzten Ausführung geändert wurde **"False"** angeben, dass die eigenschafteneinstellungen angewendet wurden, oder ignoriert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework behält nachverfolgen, von denen Seiten werden "unsaubere", d. h., die Eigenschaftenseiten für das Sie aufgerufen haben **SetModified (TRUE)**. Die Schaltfläche "jetzt" wird immer aktiviert, wenn Sie rufen **SetModified (TRUE)** für eine der Seiten. Die Schaltfläche "jetzt" wird deaktiviert, beim Aufrufen von **SetModified (FALSE)** für eine der Seiten, aber nur wenn Sie keines der anderen Seiten "unsaubere".  
  
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

