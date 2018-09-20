---
title: CDaoRecordView-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordView [MFC], CDaoRecordView
- CDaoRecordView [MFC], IsOnFirstRecord
- CDaoRecordView [MFC], IsOnLastRecord
- CDaoRecordView [MFC], OnGetRecordset
- CDaoRecordView [MFC], OnMove
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78d0dd3715ceb6a366ae1ab9ef2c2104432b30af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446093"
---
# <a name="cdaorecordview-class"></a>CDaoRecordView-Klasse

Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CDaoRecordView : public CFormView
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDaoRecordView::CDaoRecordView](#cdaorecordview)|Erstellt ein `CDaoRecordView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|Gibt, die ungleich NULL, wenn der aktuelle Datensatz den ersten Datensatz im Recordset-Objekt zugeordnet ist.|
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|Gibt, die ungleich NULL, wenn der aktuelle Datensatz den letzten Datensatz im Recordset-Objekt zugeordnet ist.|
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|Gibt einen Zeiger auf ein Objekt einer Klasse abgeleitet `CDaoRecordset`. Klassen-Assistent überschreibt diese Funktion für Sie und erstellt das Recordset, bei Bedarf.|
|[CDaoRecordView::OnMove](#onmove)|Wenn der aktuelle Datensatz geändert wurde, wird für die Datenquelle aktualisiert, und klicken Sie dann wechselt zum angegebenen Datensatz (nächsten, vorherigen, ersten oder letzten).|

## <a name="remarks"></a>Hinweise

Die Ansicht ist eine Formularansicht können Sie direkt mit verbundenen eine `CDaoRecordset` Objekt. Die Ansicht aus einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder an die `CDaoRecordset` Objekt in der Dialogfeldvorlage-Steuerelementen. Die `CDaoRecordView` Objekt verwendet Dialogdatenaustausch (DDX) und DAO-Datensatzfeldaustausch (DFX), um die Verschiebung von Daten zwischen den Steuerelementen im Formular und die Felder des Recordset-Objekts zu automatisieren. `CDaoRecordView` Außerdem stellt eine Standardimplementierung für das Verschieben von mit dem ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des Datensatzes in der Ansicht.

> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können weiterhin den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen; die DAO-Klassen bieten im Allgemeinen bessere Funktionen, da sie auf die Microsoft Jet-Datenbank-Engine verwenden.

Die gängigste Methode zum Erstellen der Datensatzansicht ist mit der Anwendungs-Assistenten. Die Anwendungs-Assistent erstellt sowohl die datensatzansichtsklasse und ihrer zugehörigen Recordset-Klasse als Teil Ihrer Skelett Starter-Anwendung.

Der Anwendungs-Assistent-Ansatz ist einfacher, wenn lediglich ein einzelnes Formular. Klassen-Assistenten können Sie die eine Datensatzansicht später im Entwicklungsprozess verwenden möchten. Wenn Sie mit der Anwendungs-Assistent die datensatzansichtsklasse erstellen, können Sie es später noch Mal mit Klassen-Assistenten erstellen. Mithilfe der Klassen-Assistent zum Erstellen einer Datensatzansicht und ein Recordset getrennt, und verbinden Sie sie dann die flexibelste Herangehensweise ist, denn es Ihnen mehr Kontrolle ermöglicht bei der Benennung der Recordset-Klasse und die zugehörige. H /. CPP-Dateien. Dadurch können auch mehrere Datensatzansichten für die gleiche Recordsetklasse zu haben.

Um für Endbenutzer zum Verschieben von Datensatz zu Datensatz in der Datensatzansicht erleichtern, die Anwendungs-Assistent erstellt, Menü (und optional einer Symbolleiste) Ressourcen für den Umstieg auf das erste, nächsten, vorherigen oder letzten Datensatz. Wenn Sie eine datensatzansichtsklasse mit Klassen-Assistenten erstellen, müssen Sie diese Ressourcen sich selbst mit dem Menü und die Bitmap Editoren zu erstellen.

Informationen über die standardmäßige Implementierung für das Verschieben von Datensatz zu Datensatz, finden Sie unter `IsOnFirstRecord` und `IsOnLastRecord` und im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md), die für beide gilt `CRecordView` und `CDaoRecordView`.

`CDaoRecordView` behält den Überblick Position des Benutzers im Recordset, damit der Datensatzansicht angezeigt, die Benutzeroberfläche aktualisieren kann. Wenn der Benutzer an beiden Enden des Recordsets verschiebt, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte – z. B. Menüelemente und Symbolleisten-Schaltflächen, für das Verschieben von weiter in die gleiche Richtung.

Weitere Informationen zu deklarieren und verwenden Ihre Datensätze anzeigen und das Recordset-Klassen finden Sie unter "Entwerfen und Erstellen einer Datensatzansicht" in diesem Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md). Weitere Informationen zu wie von Datensatzansichten und deren Verwendung finden Sie im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md). Alle oben genannten Artikel gelten für beide `CRecordView` und `CDaoRecordView`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CDaoRecordView`

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

##  <a name="cdaorecordview"></a>  CDaoRecordView::CDaoRecordView

Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `CDaoRecordView`, rufen Sie entweder Form des Konstruktors initialisiert das Objekt, und identifizieren die Ressource auf dem die Sicht basiert.

```
explicit CDaoRecordView(LPCTSTR lpszTemplateName);
explicit CDaoRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parameter

*lpszTemplateName*<br/>
Enthält eine Null-terminierte Zeichenfolge, die den Namen der einer Dialogfeldvorlagen-Ressource ist.

*nIDTemplate*<br/>
Enthält die ID einer Dialogfeldvorlagen-Ressource.

### <a name="remarks"></a>Hinweise

Sie können entweder die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine Ganzzahl ohne Vorzeichen als Argument) identifizieren. Eine Ressource ist die ID empfohlen.

> [!NOTE]
>  Die abgeleitete Klasse muss seinen eigenen Konstruktor angeben. Rufen Sie im Konstruktor einer abgeleiteten Klasse den Konstruktor `CDaoRecordView::CDaoRecordView` mit Ressourcenname oder ID als Argument.

`CDaoRecordView::OnInitialUpdate` Aufrufe `CWnd::UpdateData`, welche Aufrufe `CWnd::DoDataExchange`. Dieser anfänglichen Aufruf `DoDataExchange` verbindet `CDaoRecordView` steuert (indirekt) zu `CDaoRecordset` Feld Datenmember von Klassen-Assistent erstellt. Diese Datenelemente nicht erst verwendet werden, nach dem Aufruf der Basisklasse `CFormView::OnInitialUpdate` Member-Funktion.

> [!NOTE]
>  Wenn Sie die Klassen-Assistenten verwenden, wird der Assistent definiert eine **Enum** Wert `CDaoRecordView::IDD` in der Deklaration der Klasse und verwendet, die sie bei der Memberinitialisierung auflisten, für den Konstruktor.

[!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]

##  <a name="isonfirstrecord"></a>  CDaoRecordView::IsOnFirstRecord

Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz den ersten Datensatz im Recordset-Objekt, das dieser Datensatzansicht zugeordnet ist.

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der aktuelle Datensatz den ersten Datensatz im Recordset ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion ist nützlich für das Schreiben eigener Implementierungen der Standard-Update-Befehlshandler von Datensatzfeldern von ClassWizard geschrieben.

Wenn der Benutzer zum ersten Datensatz verschoben wird, müssen die Framework-deaktiviert, die Objekte der Benutzeroberfläche (z. B. Menüelemente oder Symbolleisten-Schaltflächen) für das Verschieben in das erste oder der vorherige Datensatz.

##  <a name="isonlastrecord"></a>  CDaoRecordView::IsOnLastRecord

Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz der letzte Eintrag in das Recordset-Objekt, das dieser Datensatzansicht zugeordnet ist.

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der aktuelle Datensatz den letzten Datensatz im Recordset ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion ist nützlich für das Schreiben eigener Implementierungen der Standard-Update-Befehlshandler, die Klassen-Assistent schreibt, um eine Benutzeroberfläche für das Verschieben von Datensatz zu Datensatz zu unterstützen.

> [!CAUTION]
>  Das Ergebnis dieser Funktion ist zuverlässig, mit dem Unterschied, dass die Ansicht möglicherweise nicht erkennen Sie das Ende des Recordset-Objekts, bis der Benutzer, fügen Sie ihn verschoben wurde. Der Benutzer möglicherweise hinter dem letzten Datensatz zu verschieben, bevor die Datensatzansicht erkennen kann, müssen sie alle Benutzeroberflächenobjekte für das Verschieben in den nächsten oder letzten Datensatz deaktivieren. Wenn der Benutzer hinter dem letzten Datensatz verschoben wird, und klicken Sie dann zurück zum letzten Datensatz wechselt (oder davor), kann die Datensatzansicht verfolgen die Position des Benutzers im Recordset und Benutzeroberflächenobjekte ordnungsgemäß deaktiviert.

##  <a name="ongetrecordset"></a>  CDaoRecordView::OnGetRecordset

Gibt einen Zeiger auf die `CDaoRecordset`-abgeleitete Objekt, mit der Datensatzansicht verknüpft ist.

```
virtual CDaoRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CDaoRecordset`-abgeleitetes Objekt aus, wenn das Objekt erfolgreich erstellt wurde, andernfalls wurde ein NULL-Zeiger.

### <a name="remarks"></a>Hinweise

Sie müssen diese Member-Funktion zum Erstellen oder einem Recordset-Objekt zu erhalten, und geben einen Zeiger auf die sie überschreiben. Wenn Sie die datensatzansichtsklasse mit Klassen-Assistent deklarieren, schreibt der Assistent eine standardmäßigen Außerkraftsetzung für Sie. ClassWizard die Standardimplementierung gibt den Recordset-Zeiger, die in der Datensatzansicht gespeichert werden, sofern vorhanden. Wenn nicht, einem Recordset-Objekt des Typs erstellt angegebenen mit Klassen-Assistent und ruft seine `Open` Member Funktion, um öffnen Sie die Tabelle, oder führen Sie die Abfrage, und klicken Sie dann einen Zeiger auf das Objekt zurück.

Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).

##  <a name="onmove"></a>  CDaoRecordView::OnMove

Rufen Sie diese Memberfunktion zum Verschieben in einen anderen Datensatz im Recordset, und die Felder in die Steuerelemente der Datensatzansicht angezeigt.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parameter

*nIDMoveCommand*<br/>
Einer der folgenden Standardbefehle-ID-Werte:

- ID_RECORD_FIRST verschieben in den ersten Datensatz im Recordset.

- ID_RECORD_LAST verschieben in den letzten Datensatz im Recordset.

- ID_RECORD_NEXT verschieben in den nächsten Datensatz im Recordset.

- ID_RECORD_PREV verschieben in den vorherigen Datensatz im Recordset.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Verschiebung erfolgreich war; andernfalls 0, wenn die verschiebungsanforderung abgelehnt wurde.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung Ruft die entsprechenden Move-Memberfunktion auf, der die `CDaoRecordset` Objekt, mit der Datensatzansicht verknüpft ist.

In der Standardeinstellung `OnMove` des aktuellen Datensatzes in der Datenquelle aktualisiert, wenn der Benutzer es in der Datensatzansicht geändert hat.

Die Anwendungs-Assistent erstellt eine Menüressource ersten, letzten Datensatz, nächsten Datensatz, und vorherigen Datensatz von Menüelementen an. Wenn Sie die erste Symbolleiste-Option auswählen, erstellt der Anwendungs-Assistent auch eine Symbolleiste mit Schaltflächen, die auf diese Befehle entspricht.

Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, wird die Datensatzansicht weiterhin den letzten Datensatz angezeigt. Wenn Sie nach den ersten Datensatz rückwärts verschieben, wird die Datensatzansicht weiterhin den ersten Datensatz angezeigt.

> [!CAUTION]
>  Aufrufen von `OnMove` löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Rufen Sie die entsprechende Schnittstelle Update-Handler-Funktion – `OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`, oder `OnUpdateRecordPrev` , verschieben Sie vor der entsprechenden Vorgang bestimmt, ob das Recordset alle Datensätze ist.

## <a name="see-also"></a>Siehe auch

[CFormView-Klasse](../../mfc/reference/cformview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CFormView-Klasse](../../mfc/reference/cformview-class.md)
