---
title: COleDBRecordView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE DB
- COleDBRecordView class
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
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
ms.openlocfilehash: 89b5cb175900d11854dcad03440a1ef0bfb8cff9
ms.lasthandoff: 02/24/2017

---
# <a name="coledbrecordview-class"></a>COleDBRecordView-Klasse
Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Erstellt ein `COleDBRecordView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Gibt einen `HRESULT` Wert.|  
|[COleDBRecordView::OnMove](#onmove)|Aktualisiert den aktuellen Datensatz (falls modifizierte) für die Datenquelle und dann zum angegebenen Datensatz (nächsten, vorherigen, ersten oder letzten).|  
  
## <a name="remarks"></a>Hinweise  
 Die Ansicht ist eine direkte Verbindung zum Formularansicht ein `CRowset` Objekt. Die Ansicht einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder an die `CRowset` Objekt in der Dialogfeldvorlagen-Steuerelementen. Die `COleDBRecordView` -Objekt verwendet den Dialogdatenaustausch (DDX) und die Navigationsfunktionen `CRowset`, um die Verschiebung von Daten zwischen den Steuerelementen auf dem Formular und den Feldern des Rowsets zu automatisieren. `COleDBRecordView`liefert auch eine Standardimplementierung für einen Wechsel zum ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren der aktuell angezeigten Datensatzes.  
  
 Sie können DDX-Funktionen mit **COleDbRecordView** Daten direkt aus der Datenbankrecordset abrufen und in einem Dialogfeld-Steuerelement anzeigt. Verwenden Sie die **DDX_\* ** Methoden (z. B. `DDX_Text`), nicht die **DDX_Field\* ** Funktionen (z. B. `DDX_FieldText`) mit **COleDbRecordView**. `DDX_FieldText`funktioniert nicht mit **COleDbRecordView** da `DDX_FieldText` nimmt ein zusätzliches Argument vom Typ **CRecordset\* ** (für `CRecordView`) oder **CDaoRecordset\* ** (für `CDaoRecordView`).  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der OLE DB-Consumervorlagen-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView`behält Verfolgen der Position des Benutzers im Rowset, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann. Wechselt der Benutzer an beiden Enden des Rowsets, deaktiviert die Datensatzansicht Benutzer Schnittstelle Objekte Â €"z. B. Menüeinträge oder Symbolleiste Schaltflächen Â €" für das Verschieben von weiter in die gleiche Richtung.  
  
 Weitere Informationen zum Schemarowset-Klassen finden Sie unter der [mithilfe von OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) Artikel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView  
 Erstellt ein `COleDBRecordView`-Objekt.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine auf Null endende Zeichenfolge, die den Namen einer Dialogfeldvorlagen-Ressource ist.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `COleDBRecordView`, rufen Sie die Konstruktoren das View-Objekt erstellen und identifizieren die Dialogfeldressource, auf denen die Sicht basiert. Sie können die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine ganze Zahl als Argument) identifizieren.  
  
> [!NOTE]
>  Die abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. Rufen Sie im Konstruktor den Konstruktor `COleDBRecordView::COleDBRecordView`, mit dem Ressourcennamen oder die ID als Argument.  
  
##  <a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 Gibt ein Handle für die **CRowset<> </> ** Objekt, das mit der Datensatzansicht zugeordnet.  
  
```  
virtual CRowset<>* OnGetRowset(Â) = 0;  
 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Memberfunktion zum Erstellen oder ein Rowset-Objekt zu erhalten und ein Handle zurück, zu überschreiben. Wenn Sie Datensatzansichts-Klasse mit dem Klassen-Assistenten deklariert haben, schreibt der Assistent eine Standard-Außerkraftsetzung für Sie. Die standardmäßige Implementierung des Klassen-Assistent gibt das Rowset-Handle, das in der Datensatzansicht gespeichert, sofern vorhanden. Wenn nicht, er ein Rowset-Objekt des Typs erstellt angegebenen mit dem Klassen-Assistenten und ruft seine **öffnen** Element funktioniert, öffnen Sie die Tabelle, oder führen die Abfrage und gibt ein Handle für das Objekt.  
  
> [!NOTE]
>  Vor MFC 7.0 `OnGetRowset` zurückgegeben, einen Zeiger auf `CRowset`. Wenn Sie über Code verfügen, die Aufrufe `OnGetRowset`, müssen Sie den Rückgabetyp der templatized Klasse ändern **CRowset<>**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#38;](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>COleDBRecordView::OnMove  
 Wechselt zu einem anderen Datensatz in das Rowset und die Anzeige der Felder in den Steuerelementen des Datensatzes anzeigen  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDMoveCommand`  
 Einer der folgenden Standardbefehls-ID-Werte:  
  
- `ID_RECORD_FIRST`Â Â Â verschieben, auf den ersten Datensatz im Recordset.  
  
- `ID_RECORD_LAST`Â Â Â wechselt zur letzten Datensatz im Recordset.  
  
- `ID_RECORD_NEXT`Â Â Â verschieben, auf den nächsten Datensatz im Recordset.  
  
- `ID_RECORD_PREV`Â Â Â verschieben in den vorherigen Datensatz im Recordset.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verschiebung erfolgreich war; andernfalls 0, wenn die Move-Anforderung verweigert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft die entsprechende **verschieben** Memberfunktion der `CRowset` Objekt, das mit der Datensatzansicht zugeordnet.  
  
 In der Standardeinstellung `OnMove` den aktuellen Datensatz in der Datenquelle aktualisiert, wenn der Benutzer in der Datensatzansicht geändert hat.  
  
 Der Assistent erstellt eine Menüressource mit ersten, letzten Datensatz, nächsten Datensatz, und vorherigen Datensatz Menüelemente. Wenn Sie die Option andockbare Symbolleiste auswählen, erstellt der Assistent der Anwendung auch eine Symbolleiste mit Schaltflächen, die für diese Befehle.  
  
 Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, wird die Datensatzansicht weiterhin den letzten Datensatz angezeigt. Wenn Sie nach dem ersten Datensatz rückwärts verschieben, können Sie weiterhin die Datensatzansicht des ersten Datensatzes angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




