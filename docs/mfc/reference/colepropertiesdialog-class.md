---
title: Klasse COlePropertiesDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE Object Properties dialog box
- Object Properties dialog box
- dialog boxes, OLE
- OLE documents, modifying properties
- property pages, OLE
- COlePropertiesDialog class
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0c07766bca6bbc546f877e10255d80bd388d30d7
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog-Klasse
Kapselt das allgemeine Windows-OLE-Dialogfeld "Objekteigenschaften".  
  
## <a name="syntax"></a>Syntax  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Erstellt ein `COlePropertiesDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Wird vom Framework aufgerufen, wenn die Skalierung des Dokumentelements geändert hat.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|Eine Struktur, die zum Initialisieren der Seite "Allgemein" verwendet ein `COlePropertiesDialog` Objekt.|  
|[COlePropertiesDialog::m_lp](#m_lp)|Eine Struktur, die zum Initialisieren der Seite "Link" verwendet ein `COlePropertiesDialog` Objekt.|  
|[COlePropertiesDialog::m_op](#m_op)|Eine Struktur, die zum Initialisieren der `COlePropertiesDialog` Objekt.|  
|[COlePropertiesDialog::m_psh](#m_psh)|Eine Struktur verwendet, um zusätzliche benutzerdefinierte Eigenschaftenseiten hinzuzufügen.|  
|[COlePropertiesDialog::m_vp](#m_vp)|Eine Struktur zum Anpassen der Seite "View" von einem `COlePropertiesDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Allgemeine Eigenschaften für das OLE-Objekts Dialogfelder bieten eine einfache Möglichkeit zum Anzeigen und Ändern der Eigenschaften von einem OLE-Dokument-Element in Übereinstimmung mit den Windows-Standards. Diese Eigenschaften umfassen u. a. Informationen über die Datei, die durch das Dokumentelement Optionen zum Anzeigen von Symbol und Bildskalierung und Informationen auf der Link des Elements (wenn das Element verknüpft ist) dargestellt.  
  
 Verwenden einer `COlePropertiesDialog` Objekt erstellen Sie zunächst das Objekt mit dem `COlePropertiesDialog` Konstruktor. Nachdem das Dialogfeld erstellt wurde, rufen Sie die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen, und ermöglichen den Benutzer, alle Eigenschaften des Elements ändern. `DoModal`Gibt zurück, ob der Benutzer OK ausgewählt ( **IDOK**) oder Abbrechen ( **IDCANCEL**) Schaltfläche. Neben den Schaltflächen OK und Abbrechen befindet sich eine Schaltfläche anwenden. Bei der Auswahl anwenden, werden alle Änderungen an den Eigenschaften des Dokumentelements für das Element angewendet, und seine Bild wird automatisch aktualisiert, sondern bleibt aktiv.  
  
 Die [M_psh](#m_psh) -Datenmember ist ein Zeiger auf eine **PROPSHEETHEADER** -Struktur in den meisten Fällen Sie nicht explizit darauf zugreifen müssen. Eine Ausnahme ist benötigen Sie zusätzliche Eigenschaftenseiten über die Standardseiten Allgemein, anzeigen und verknüpfen. In diesem Fall können Sie ändern die `m_psh` Datenmember enthalten persönliche Seiten vor dem Aufruf der `DoModal` Member-Funktion.  
  
 Weitere Informationen zu OLE-Dialogfelder, finden Sie im Artikel [Dialogfelder in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxodlgs.h  
  
##  <a name="a-namecolepropertiesdialoga--colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog  
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
 Maximale Skalierung Prozentsatz für das Bild der Dokument-Element.  
  
 `pParentWnd`  
 Ein Zeiger auf des Dialogfelds über- oder Besitzer.  
  
### <a name="remarks"></a>Hinweise  
 Leiten Sie die allgemeinen Eigenschaften für das OLE-Objekts Dialogfeldklasse aus `COlePropertiesDialog` um für Ihre Dokumentelemente Skalierung zu implementieren. Alle Dialogfelder, die von einer Instanz dieser Klasse implementiert unterstützt das Dokumentelement Skalierung nicht.  
  
 Das Dialogfeld Allgemeine Eigenschaften für das OLE-Objekts verfügt standardmäßig über drei Standardseiten:  
  
-   Allgemein  
  
     Diese Seite enthält Informationen für die Datei, die durch das ausgewählte Dokument-Element dargestellt wird. Auf dieser Seite kann Benutzer das ausgewählte Element in einen anderen Typ konvertieren.  
  
-   Ansicht  
  
     Diese Seite enthält Optionen für das Element anzuzeigen, ändern das Symbol und die Skalierung des Bilds.  
  
-   Link  
  
     Diese Seite enthält Optionen zum Ändern des Speicherorts für das verknüpfte Element, und aktualisieren das verknüpfte Element. Auf dieser Seite kann die Benutzer die Verknüpfung des ausgewählten Elements unterbrechen.  
  
 Neben den standardmäßig bereitgestellten Seiten hinzufügen, ändern die [M_psh](#m_psh) Membervariable vor dem Beenden des Konstruktors der Ihre `COlePropertiesDialog`-abgeleiteten Klasse. Dies ist eine erweiterte Implementierung von der `COlePropertiesDialog` Konstruktor.  
  
##  <a name="a-namedomodala--colepropertiesdialogdomodal"></a><a name="domodal"></a>COlePropertiesDialog::DoModal  
 Rufen Sie diese Memberfunktion zum Windows-das Dialogfeld Allgemeine Eigenschaften für das OLE-Objekts anzuzeigen und dem Benutzer ermöglichen, anzeigen und/oder ändern die verschiedenen Eigenschaften des Dokumentelements.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL** Wenn erfolgreich, andernfalls 0. **IDOK** und **IDCANCEL** Konstanten, die angeben, ob der Benutzer auf die Schaltfläche OK oder Abbrechen ausgewählt werden.  
  
 Wenn **IDCANCEL** zurückgegeben wird, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.  
  
##  <a name="a-namemgpa--colepropertiesdialogmgp"></a><a name="m_gp"></a>COlePropertiesDialog::m_gp  
 Eine Struktur vom Typ [OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), mit die Seite Allgemein im Dialogfeld Eigenschaften für das OLE-Objekt zu initialisieren.  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Seite zeigt den Typ und die Größe einer einbetten und ermöglicht es den Benutzerzugriff auf das Dialogfeld konvertieren. Auf dieser Seite werden auch Ziel des Links, wenn das Objekt ein Link ist.  
  
 Weitere Informationen zu den **OLEUIGNRLPROPS** -Struktur, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemlpa--colepropertiesdialogmlp"></a><a name="m_lp"></a>COlePropertiesDialog::m_lp  
 Eine Struktur vom Typ [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), mit denen die Link-Seite des Dialogfelds Eigenschaften für das OLE-Objekt zu initialisieren.  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Seite zeigt die Position des verknüpften Elements und ermöglicht es dem Benutzer zu aktualisieren oder zu unterbrechen, den Link, um das Element.  
  
 Weitere Informationen zu den **OLEUILINKPROPS** -Struktur, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemopa--colepropertiesdialogmop"></a><a name="m_op"></a>COlePropertiesDialog::m_op  
 Eine Struktur vom Typ [OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199)verwendet, um das Dialogfeld Allgemeine Eigenschaften für das OLE-Objekts initialisieren.  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Struktur enthält Elemente, die zum Initialisieren von der Seiten Allgemein, verknüpfen und anzeigen.  
  
 Weitere Informationen finden Sie unter der **OLEUIOBJECTPROPS** und [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735) Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namempsha--colepropertiesdialogmpsh"></a><a name="m_psh"></a>COlePropertiesDialog::m_psh  
 Eine Struktur vom Typ [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546), zu speichern, deren Mitglieder die Merkmale des Dialog-Objekts.  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `COlePropertiesDialog` -Objekt können Sie `m_psh` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der `DoModal` Member-Funktion.  
  
 Wenn Sie ändern die `m_psh` Datenmember direkt Standardverhalten überschreiben.  
  
 Weitere Informationen zu den **PROPSHEETHEADER** -Struktur, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemvpa--colepropertiesdialogmvp"></a><a name="m_vp"></a>COlePropertiesDialog::m_vp  
 Eine Struktur vom Typ [OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751)verwendet, um die Seite Sicht im Dialogfeld Eigenschaften für das OLE-Objekt zu initialisieren.  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>Hinweise  
 Auf dieser Seite können die Benutzer Umschalten zwischen "Content" und "iconic" Ansichten des Objekts, und ändern Sie die Skalierung innerhalb des Containers. Es kann auch den Benutzerzugriff auf das Dialogfeld "Symbol ändern", wenn das Objekt als Symbol angezeigt wird.  
  
 Weitere Informationen zu den **OLEUIVIEWPROPS** -Struktur, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonapplyscalea--colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale  
 Wird vom Framework aufgerufen, wenn der Skalierungswert geändert hat und OK oder übernehmen ausgewählt wurde.  
  
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
 Numerische Wert der Skala Dialogfeld.  
  
 *bRelativeToOrig*  
 Gibt an, ob Skalierung für die ursprüngliche Größe des Dokumentelements gilt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null behandelt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Sie müssen diese Funktion, um die Skalierung Steuerelemente ermöglichen überschreiben.  
  
> [!NOTE]
>  Bevor das Dialogfeld Allgemeine Eigenschaften für das OLE-Objekts angezeigt wird, wird das Framework ruft diese Funktion mit einem **NULL** für `pItem` und – 1 für `nCurrentScale`. Dies erfolgt, um festzustellen, ob die Skalierung Steuerelemente aktiviert werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CIRC](../../visual-cpp-samples.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDialog-Klasse](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage-Klasse](../../mfc/reference/cpropertypage-class.md)

