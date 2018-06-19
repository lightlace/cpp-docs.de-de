---
title: COleDBRecordView-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b69aafa7f8b07d96d754d080e7fb5abd170e167
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372205"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView-Klasse
Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Erstellt ein `COleDBRecordView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Gibt eine `HRESULT` Wert.|  
|[COleDBRecordView::OnMove](#onmove)|Aktualisiert den aktuellen Datensatz (falls geändert) für die Datenquelle, und klicken Sie dann auf den angegebenen Datensatz verschoben (nächsten, vorherigen, ersten oder letzten).|  
  
## <a name="remarks"></a>Hinweise  
 Die Ansicht ist eine Formularansicht können Sie eine direkte Verbindung zum ein `CRowset` Objekt. Die Sicht aus einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder der `CRowset` Objekt in der Dialogfeldvorlage-Steuerelementen. Die `COleDBRecordView` Objekt verwendet Dialogdatenaustausch (DDX) und die Navigationsfunktionen `CRowset`, um die Verschiebung von Daten zwischen den Steuerelementen im Formular und die Felder des Rowsets zu automatisieren. `COleDBRecordView` Außerdem stellt eine Standardimplementierung für das Verschieben von mit dem ersten nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des Datensatzes derzeit für die Sicht.  
  
 Sie können DDX-Funktionen mit **COleDbRecordView** Daten direkt aus der Datenbankrecordset abrufen und in einem Dialogfeldsteuerelement anzeigt. Verwenden Sie die **DDX_\***  Methoden (z. B. `DDX_Text`), und nicht die **DDX_Field\***  Funktionen (z. B. `DDX_FieldText`) mit **COleDbRecordView** . `DDX_FieldText` funktioniert nicht mit **COleDbRecordView** da `DDX_FieldText` akzeptiert ein zusätzliches Argument vom Typ **CRecordset\***  (für `CRecordView`) oder **CDaoRecordset\***  (für `CDaoRecordView`).  
  
> [!NOTE]
>  Wenn Sie die Klassen Datenzugriffsobjekte (DAO) anstelle der OLE DB-Consumervorlagen Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView` Hält den Überblick über die Position des Benutzers im Rowset, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann. Wenn der Benutzer an einem Ende des Rowsets verschoben wird, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte – z. B. Menüelemente und Symbolleisten-Schaltflächen – zum Verschieben in die gleiche Richtung weiter.  
  
 Weitere Informationen zum Schemarowset-Klassen finden Sie unter der [mithilfe von OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) Artikel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>  COleDBRecordView::COleDBRecordView  
 Erstellt ein `COleDBRecordView`-Objekt.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine Null-terminierte Zeichenfolge, die den Namen einer Dialogfeldvorlagen-Ressource ist.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `COleDBRecordView`, Aufrufen eines Konstruktors erstellen das Ansichtsobjekt und identifizieren die Dialogressource, auf denen die Sicht basiert. Sie können die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine Ganzzahl ohne Vorzeichen als Argument) identifizieren.  
  
> [!NOTE]
>  Die abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. In den Konstruktor aufrufen des Konstruktors und `COleDBRecordView::COleDBRecordView`, mit dem Ressourcennamen oder die ID als Argument.  
  
##  <a name="ongetrowset"></a>  COleDBRecordView::OnGetRowset  
 Gibt ein Handle für die **CRowset <>** Objekt, das mit der Datensatzansicht zugeordnet.  
  
```  
virtual CRowset<>* OnGetRowset() = 0;  
 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Memberfunktion zum Erstellen oder ein Rowsetobjekt abzurufen und ein Handle zu einer zurückkehren, überschreiben. Wenn Sie die datensatzansichtsklasse mit ClassWizard deklarieren, schreibt der Assistent eine Standard-Außerkraftsetzung für Sie. ClassWizard die standardmäßige Implementierung gibt das Rowset-Handle, das in der Datensatzansicht gespeichert werden, sofern vorhanden. Wenn nicht, es eine Rowset-Objekte des Typs erstellt angegebenen mit ClassWizard und ruft seine **öffnen** Member Funktion, um öffnen Sie die Tabelle, oder führen Sie die Abfrage, und klicken Sie dann ein Handle für das Objekt zurückgegeben.  
  
> [!NOTE]
>  "Zurück", MFC 7.0 `OnGetRowset` zurückgegeben wird einen Zeiger auf `CRowset`. Wenn Sie über Code verfügen, die aufruft `OnGetRowset`, müssen Sie den Rückgabetyp der vorlagenbasierten Klasse ändern **CRowset <>**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  COleDBRecordView::OnMove  
 Wechselt zu einem anderen Datensatz im Rowset und Anzeige zeigen Sie ihre Felder in den Steuerelementen des Datensatzes an.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDMoveCommand`  
 Einer der folgenden Werte Standardbefehls-ID:  
  
- `ID_RECORD_FIRST` – Wechseln Sie zu den ersten Datensatz des Recordsets.  
  
- `ID_RECORD_LAST` – Wechselt zur letzten Datensatz des Recordsets.  
  
- `ID_RECORD_NEXT` – Verschieben Sie auf den nächsten Datensatz im Recordset.  
  
- `ID_RECORD_PREV` – Wechseln Sie zum vorherigen Datensatz im Recordset.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verschiebung erfolgreich war; andernfalls 0, wenn die Anforderung zum Verschieben von verweigert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Ruft die entsprechende **verschieben** Memberfunktion der `CRowset` Objekt, das mit der Datensatzansicht zugeordnet.  
  
 Standardmäßig `OnMove` den aktuellen Datensatz in der Datenquelle aktualisiert, wenn der Benutzer in der Datensatzansicht geändert hat.  
  
 Der Anwendungs-Assistent erstellt eine Menüressource mit ersten, letzten Datensatzes, nächsten Datensatz, und vorherigen Datensatz Menüelemente an. Wenn Sie die Option andockbare Symbolleiste auswählen, erstellt der Anwendungs-Assistent auch eine Symbolleiste mit Schaltflächen, die auf diese Befehle entspricht.  
  
 Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, weiterhin die Datensatzansicht den letzten Datensatz anzuzeigen. Wenn Sie nach dem ersten Datensatz rückwärts verschieben, können Sie weiterhin die Datensatzansicht des ersten Datensatzes angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



