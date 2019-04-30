---
title: COleDBRecordView-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: 1b09599479010f87e396e6f576c9524651923f9f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341721"
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
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Gibt einen standard-HRESULT-Wert.|
|[COleDBRecordView::OnMove](#onmove)|Aktualisiert den aktuellen Datensatz (wenn) für die Datenquelle, und klicken Sie dann auf den angegebenen Datensatz verschoben (nächsten, vorherigen, ersten oder letzten).|

## <a name="remarks"></a>Hinweise

Die Ansicht ist eine Formularansicht können Sie direkt mit verbundenen eine `CRowset` Objekt. Die Ansicht aus einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder an die `CRowset` Objekt in der Dialogfeldvorlage-Steuerelementen. Die `COleDBRecordView` Objekt verwendet Dialogdatenaustausch (DDX) aus, und die Navigationsfunktionen `CRowset`, um die Verschiebung von Daten zwischen den Steuerelementen im Formular und die Felder des Rowsets zu automatisieren. `COleDBRecordView` Außerdem stellt eine Standardimplementierung für das Verschieben von mit dem ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren der aktuell angezeigten Datensatzes.

Sie können die DDX-Funktionen mit `COleDbRecordView` um Daten direkt aus dem Datenbankrecordset abrufen und in einem Dialogfeldsteuerelement anzuzeigen. Verwenden Sie die `DDX_*` Methoden (z. B. `DDX_Text`) und nicht die `DDX_Field*` Funktionen (z. B. `DDX_FieldText`) mit `COleDbRecordView`. `DDX_FieldText` funktioniert nicht mit `COleDbRecordView` da `DDX_FieldText` nimmt ein zusätzliches Argument vom Typ `CRecordset*` (für `CRecordView`) oder `CDaoRecordset*` (für `CDaoRecordView`).

> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der OLE DB-Consumervorlagen-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).

`COleDBRecordView` behält den Überblick Position des Benutzers im Rowset, damit der Datensatzansicht angezeigt, die Benutzeroberfläche aktualisieren kann. Wenn der Benutzer an beiden Enden des Rowsets bewegt, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte – wie z. B. Menüelemente und Symbolleisten-Schaltflächen – für das Verschieben von weiter in die gleiche Richtung.

Weitere Informationen zum Schemarowset-Klassen finden Sie unter den [mithilfe von OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md) Artikel.

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

*lpszTemplateName*<br/>
Enthält eine Null-terminierte Zeichenfolge, die den Namen einer Dialogfeldvorlagen-Ressource ist.

*nIDTemplate*<br/>
Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource.

### <a name="remarks"></a>Hinweise

Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `COleDBRecordView`, rufen Sie einen der Konstruktoren verwenden, erstellen das Objekt und identifizieren die Ressource auf dem die Sicht basiert. Sie können die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine Ganzzahl ohne Vorzeichen als Argument) identifizieren.

> [!NOTE]
>  Die abgeleitete Klasse *müssen* seinen eigenen Konstruktor bereitstellen. In den Konstruktor aufrufen, den Konstruktor `COleDBRecordView::COleDBRecordView`, mit der Ressourcenname oder ID als Argument.

##  <a name="ongetrowset"></a>  COleDBRecordView::OnGetRowset

Gibt ein Handle für die **CRowset <>** Objekt, mit der Datensatzansicht verknüpft ist.

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Sie müssen diese Member-Funktion zum Erstellen oder ein Rowsetobjekt abgerufen und ein Handle zu einer zurückkehren, überschreiben. Wenn Sie die datensatzansichtsklasse mit Klassen-Assistent deklarieren, schreibt der Assistent eine standardmäßigen Außerkraftsetzung für Sie. ClassWizard die Standardimplementierung gibt das Rowset-Handle, das in der Datensatzansicht gespeichert werden, sofern vorhanden. Wenn nicht der Fall, ein Rowset-Objekt des Typs erstellt angegebenen mit Klassen-Assistent und Aufrufe der `Open` Member Funktion, um öffnen Sie die Tabelle, oder führen Sie die Abfrage, und klicken Sie dann auf das Objekt gibt ein Handle zurück.

> [!NOTE]
>  Vor MFC 7.0 `OnGetRowset` zurückgegeben, einen Zeiger auf `CRowset`. Wenn Sie über Code verfügen, die aufruft `OnGetRowset`, müssen Sie den Rückgabetyp der vorlagenbasierten Klasse ändern **CRowset <>**.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).

##  <a name="onmove"></a>  COleDBRecordView::OnMove

Wechselt zu einem anderen Datensatz im Rowset und Anzeige zeigen Sie die Felder in den Steuerelementen des Datensatzes.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parameter

*nIDMoveCommand*<br/>
Einer der folgenden Standardbefehle-ID-Werte:

- ID_RECORD_FIRST, Verschieben Sie in den ersten Datensatz im Recordset.

- ID_RECORD_LAST – Wechselt zur letzten Datensatz im Recordset.

- ID_RECORD_NEXT, Verschieben Sie in den nächsten Datensatz im Recordset.

- ID_RECORD_PREV – Verschieben Sie in den vorherigen Datensatz im Recordset.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Verschiebung erfolgreich war; andernfalls 0, wenn die verschiebungsanforderung abgelehnt wurde.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung Ruft die entsprechende `Move` Memberfunktion die `CRowset` Objekt, mit der Datensatzansicht verknüpft ist.

In der Standardeinstellung `OnMove` des aktuellen Datensatzes in der Datenquelle aktualisiert, wenn der Benutzer es in der Datensatzansicht geändert hat.

Die Anwendungs-Assistent erstellt eine Menüressource ersten, letzten Datensatz, nächsten Datensatz, und vorherigen Datensatz von Menüelementen an. Wenn Sie die Option andockbare Symbolleiste auswählen, erstellt der Assistent der Anwendung auch eine Symbolleiste mit Schaltflächen, die für diese Befehle.

Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, wird die Datensatzansicht weiterhin den letzten Datensatz angezeigt. Wenn Sie nach den ersten Datensatz rückwärts verschieben, wird die Datensatzansicht weiterhin den ersten Datensatz angezeigt.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
