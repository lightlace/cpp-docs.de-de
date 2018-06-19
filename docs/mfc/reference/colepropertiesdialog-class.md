---
title: COlePropertiesDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
dev_langs:
- C++
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d61d773e2c35bb67f34ae2b4a989a388d8b4015
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371685"
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog-Klasse
Kapselt das allgemeine Windows-OLE-Dialogfeld "Objekteigenschaften".  
  
## <a name="syntax"></a>Syntax  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Erstellt ein `COlePropertiesDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Vom Framework aufgerufen, wenn sich die Skalierung der das Dokumentelement geändert hat.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|Eine Struktur, die zum Initialisieren der Seite "Allgemein" einen `COlePropertiesDialog` Objekt.|  
|[COlePropertiesDialog::m_lp](#m_lp)|Eine Struktur, die zum Initialisieren der Seite "Link" von einem `COlePropertiesDialog` Objekt.|  
|[COlePropertiesDialog::m_op](#m_op)|Eine Struktur, die zur Initialisierung der `COlePropertiesDialog` Objekt.|  
|[COlePropertiesDialog::m_psh](#m_psh)|Eine Struktur verwendet, zusätzliche benutzerdefinierte Eigenschaftenseiten hinzuzufügen.|  
|[COlePropertiesDialog::m_vp](#m_vp)|Eine Struktur, die zum Anpassen der Seite "View" verwendet eine `COlePropertiesDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Allgemeine Eigenschaften für das OLE-Objekts Dialogfelder bieten eine einfache Möglichkeit zum Anzeigen und ändern die Eigenschaften eines Elements ein OLE-Dokument in Übereinstimmung mit den Windows-Standards. Diese Eigenschaften umfassen u. a. Informationen für die Datei, die durch das Dokumentelement Anzeigeoptionen für das Symbol und Bildskalierung sowie Informationen auf den Link des Elements (sofern das Element verknüpft ist) dargestellt.  
  
 Verwenden einer `COlePropertiesDialog` Objekt, erstellen Sie zunächst das Objekt mit dem `COlePropertiesDialog` Konstruktor. Nachdem das Dialogfeld erstellt wurde, rufen Sie die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen, und ermöglicht dem Benutzer alle Eigenschaften des Elements ändern. `DoModal` Gibt zurück, ob der Benutzer die OK ausgewählt ( **IDOK**) oder die "Abbrechen" ( **IDCANCEL**) Schaltfläche. Zusätzlich zu den Schaltflächen "OK" und "Abbrechen" wird es eine Schaltfläche "anwenden". Wenn der Benutzer übernehmen auswählt, werden alle Änderungen an den Eigenschaften des Dokumentelements auf das Element angewendet und seines Abbilds wird automatisch aktualisiert, jedoch bleibt aktiv.  
  
 Die [M_psh](#m_psh) -Datenmember ist ein Zeiger auf eine **PROPSHEETHEADER** -Struktur, und in den meisten Fällen Sie nicht explizit Zugriff darauf müssen. Eine Ausnahme ist bei Bedarf zusätzliche Eigenschaftenseiten hinter den Standardseiten für allgemeine, Ansicht und Link. In diesem Fall können Sie ändern die `m_psh` Datenmember, schließen Ihren benutzerdefinierten Seiten vor dem Aufruf der `DoModal` Memberfunktion.  
  
 Weitere Informationen zu OLE-Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="colepropertiesdialog"></a>  COlePropertiesDialog::COlePropertiesDialog  
 Erstellt ein `COlePropertiesDialog`-Objekt.  
  
```  
COlePropertiesDialog(
    COleClientItem* pItem,  
    UINT nScaleMin = 10,  
    UINT nScaleMax = 500,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Dokumentelement, dessen Eigenschaften zugegriffen wird.  
  
 *nScaleMin*  
 Minimale Skalierung Prozentsatz für das Bild der Dokument-Element.  
  
 *nScaleMax*  
 Der maximale Prozentsatz für das Dokument Elementbild Skalierung.  
  
 `pParentWnd`  
 Ein Zeiger auf den übergeordneten oder den Besitzer des Dialogfelds.  
  
### <a name="remarks"></a>Hinweise  
 Leiten Sie eine allgemeine Eigenschaften für das OLE-Objekts Dialogfeldklasse aus `COlePropertiesDialog` um Skalierung für Ihre Dokumentelemente zu implementieren. Alle Dialogfelder, die von einer Instanz dieser Klasse implementiert unterstützt das Dokumentelement Skalierung nicht.  
  
 Standardmäßig verfügt das Standarddialogfeld OLE-Objekteigenschaften drei Standardseiten:  
  
-   Allgemein  
  
     Diese Seite enthält Systeminformationen für die Datei, die durch das ausgewählte Dokument-Element dargestellt wird. Auf dieser Seite kann die Benutzer das ausgewählte Element in einen anderen Typ konvertieren.  
  
-   Ansicht  
  
     Diese Seite enthält Optionen für das Element anzuzeigen, ändern das Symbol und Ändern der Skalierung des Bilds.  
  
-   Link  
  
     Diese Seite enthält Optionen zum Ändern des Speicherorts des verknüpften Elements und aktualisieren das verknüpfte Element. Auf dieser Seite kann die Benutzer die Verknüpfung des ausgewählten Elements unterbrechen.  
  
 Um Seiten jenseits der standardmäßig bereitgestellten hinzufügen, ändern Sie die [M_psh](#m_psh) Membervariable vor dem Beenden des Konstruktors des Ihrer `COlePropertiesDialog`-abgeleitete Klasse. Dies ist eine erweiterte Implementierung von der `COlePropertiesDialog` Konstruktor.  
  
##  <a name="domodal"></a>  COlePropertiesDialog::DoModal  
 Rufen Sie diese Memberfunktion für die Anzeige von Eigenschaften für das OLE-Objekts-Standarddialogfeld Windows und ermöglicht dem Benutzer anzeigen und/oder ändern die verschiedenen Eigenschaften des Dokumentelements.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL** Wenn erfolgreich, andernfalls 0. **IDOK** und **IDCANCEL** sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder "Abbrechen" ausgewählt.  
  
 Wenn **IDCANCEL** zurückgegeben wird, können Sie die Windows aufrufen [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um festzustellen, ob ein Fehler aufgetreten.  
  
##  <a name="m_gp"></a>  COlePropertiesDialog::m_gp  
 Eine Struktur des Typs [OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), das zum Initialisieren der Seite Allgemein im Dialogfeld Eigenschaften für das OLE-Objekts verwendet.  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Seite zeigt den Typ und die Größe einer einbetten und ermöglicht es den Benutzerzugriff auf das Dialogfeld "konvertieren". Auf dieser Seite werden auch Linkziels, wenn das Objekt einen Link handelt.  
  
 Weitere Informationen zu den **OLEUIGNRLPROPS** -Struktur, finden Sie im Windows SDK.  
  
##  <a name="m_lp"></a>  COlePropertiesDialog::m_lp  
 Eine Struktur des Typs [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), die zum Initialisieren der Seite Link im Dialogfeld Eigenschaften für das OLE-Objekts verwendet.  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Seite zeigt den Speicherort des verknüpften Elements und ermöglicht es dem Benutzer zu aktualisieren oder zu unterbrechen, den Link, um das Element.  
  
 Weitere Informationen zu den **OLEUILINKPROPS** -Struktur, finden Sie im Windows SDK.  
  
##  <a name="m_op"></a>  COlePropertiesDialog::m_op  
 Eine Struktur des Typs [OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199), initialisieren Sie das Dialogfeld Allgemeine Eigenschaften für das OLE-Objekts verwendet.  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Struktur enthält Elemente, die verwendet, um die Seiten Allgemein, links und Ansicht zu initialisieren.  
  
 Weitere Informationen finden Sie unter der **OLEUIOBJECTPROPS** und [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735) Strukturen im Windows SDK.  
  
##  <a name="m_psh"></a>  COlePropertiesDialog::m_psh  
 Eine Struktur des Typs [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546), zu speichern, deren Mitglieder die Merkmale des Dialog-Objekts.  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `COlePropertiesDialog` -Objekt können Sie `m_psh` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der `DoModal` Memberfunktion.  
  
 Wenn Sie ändern die `m_psh` Datenmember direkt, Sie Standardverhalten überschreiben.  
  
 Weitere Informationen zu den **PROPSHEETHEADER** -Struktur, finden Sie im Windows SDK.  
  
##  <a name="m_vp"></a>  COlePropertiesDialog::m_vp  
 Eine Struktur des Typs [OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751), das zum Initialisieren der Seite zum Anzeigen des Dialogfelds Eigenschaften für das OLE-Objekts verwendet.  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Auf dieser Seite können den Benutzer Umschalten zwischen der "Content" und "Symbol" Sichten des Objekts, und Ändern der Skalierung innerhalb des Containers. Zudem können den Benutzerzugriff auf das Dialogfeld "Symbol ändern", wenn das Objekt als Symbol angezeigt wird.  
  
 Weitere Informationen zu den **OLEUIVIEWPROPS** -Struktur, finden Sie im Windows SDK.  
  
##  <a name="onapplyscale"></a>  COlePropertiesDialog::OnApplyScale  
 Vom Framework aufgerufen, wenn der Skalierungswert geändert wurde und OK oder übernehmen ausgewählt wurde.  
  
```  
virtual BOOL OnApplyScale(
    COleClientItem* pItem,  
    int nCurrentScale,  
    BOOL bRelativeToOrig);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf das Dokumentelement, dessen Eigenschaften zugegriffen wird.  
  
 `nCurrentScale`  
 Numerischen Wert der Skala Dialogfeld.  
  
 *bRelativeToOrig*  
 Gibt an, ob die Skalierung für die ursprüngliche Größe des Dokumentelements gilt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null behandelt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen diese Funktion, um die Skalierung Steuerelemente ermöglichen überschreiben.  
  
> [!NOTE]
>  Bevor Sie das Dialogfeld Allgemeine Eigenschaften für das OLE-Objekts angezeigt wird, wird das Framework ruft diese Funktion mit einem **NULL** für `pItem` und a - 1 für `nCurrentScale`. Dies erfolgt, um festzustellen, ob die Skalierung Steuerelemente aktiviert werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CIRC](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage-Klasse](../../mfc/reference/cpropertypage-class.md)
