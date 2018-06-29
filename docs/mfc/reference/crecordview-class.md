---
title: CRecordView-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CRecordView [MFC], CRecordView
- CRecordView [MFC], IsOnFirstRecord
- CRecordView [MFC], IsOnLastRecord
- CRecordView [MFC], OnGetRecordset
- CRecordView [MFC], OnMove
- CRecordView [MFC], OnMove
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3d040f2da622cbfd6d1577729861917a5a03270
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079146"
---
# <a name="crecordview-class"></a>CRecordView-Klasse
Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordView::CRecordView](#crecordview)|Erstellt ein `CRecordView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|Gibt einen Wert ungleich NULL, wenn der aktuelle Datensatz der erste Datensatz im zugehörigen Recordset ist.|  
|[CRecordView::IsOnLastRecord](#isonlastrecord)|Gibt einen Wert ungleich NULL, wenn der aktuelle Datensatz der letzte Datensatz in der zugehörigen Recordset ist.|  
|[CRecordView::OnGetRecordset](#ongetrecordset)|Gibt einen Zeiger auf ein Objekt einer Klasse abgeleitet `CRecordset`. Klassen-Assistent überschreibt diese Funktion für Sie und erstellt das Recordset, bei Bedarf.|  
|[CRecordView::OnMove](#onmove)||  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordView::OnMove](#onmove)|Wenn der aktuelle Datensatz geändert hat, wird für die Datenquelle aktualisiert, und klicken Sie dann wechselt zum angegebenen Datensatz (nächsten, vorherigen, ersten oder letzten).|  
  
## <a name="remarks"></a>Hinweise  
 Die Ansicht ist eine Formularansicht können Sie eine direkte Verbindung zum ein `CRecordset` Objekt. Die Sicht aus einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder der `CRecordset` Objekt in der Dialogfeldvorlage-Steuerelementen. Die `CRecordView` -Objekt verwendet den Dialogdatenaustausch (DDX) und Datensatzfeldaustausch (RFX) zum Automatisieren der Verschiebung von Daten zwischen den Steuerelementen im Formular und die Felder des Recordsets. `CRecordView` Außerdem stellt eine Standardimplementierung für das Verschieben von mit dem ersten nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des Datensatzes derzeit für die Sicht.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Die gängigste Methode zum Erstellen der Datensatzansicht ist mit dem Anwendungs-Assistenten. Dann Anwendungs-Assistent erstellt die datensatzansichtsklasse und seiner zugehörigen Recordset-Klasse als Teil Ihrer Anwendung das Gerüst eines Starter. Wenn Sie die datensatzansichtsklasse mit dem Assistenten zum Erstellen, können Sie es später mit ClassWizard erstellen. Wenn Sie einfach ein einzelnes Formular benötigen, ist der Anwendungs-Assistent-Ansatz vereinfacht. Klassen-Assistenten können Sie die eine Datensatzansicht später im Entwicklungsprozess verwenden möchten. Die flexibelste Herangehensweise wird mithilfe der Klassen-Assistent zum Erstellen einer Datensatzansicht und ein Recordset getrennt und dann eine Verbindung herstellen, denn es Ihnen mehr Kontrolle ermöglicht bei der Benennung der Recordset-Klasse und ihre. H /. CPP-Dateien. Dieser Ansatz können auch mehrere Datensatzansichten in der gleichen Recordsetklasse verfügen.  
  
 Um Möglichkeit zum Verschieben von Datensatz zu Datensatz in der Datensatzansicht zu erleichtern, erstellt der Assistent Anwendung Menü-(und optional) zum Verschieben von Ressourcen mit dem ersten nächsten, vorherigen oder letzten Datensatz. Wenn Sie eine datensatzansichtsklasse mit ClassWizard erstellen, müssen Sie diese Ressourcen selbst mit dem Menü und Bitmap-Editor erstellen.  
  
 Informationen über die standardmäßige Implementierung für das Verschieben von Datensatz zu Datensatz finden Sie unter `IsOnFirstRecord` und `IsOnLastRecord` und im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView` behält den Überblick über die Position des Benutzers im Recordset, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann. Wenn der Benutzer an beiden Enden des Recordsets verschoben wird, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte – z. B. Menüelemente und Symbolleisten-Schaltflächen – zum Verschieben in die gleiche Richtung weiter.  
  
 Weitere Informationen zu deklarieren und Verwenden der Datensatzansicht und Recordset-Klassen, finden Sie unter "Entwerfen und Erstellen einer Datensatzansicht" im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md). Weitere Informationen wie von Datensatzansichten und deren Verwendung finden Sie im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="crecordview"></a>  CRecordView::CRecordView  
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `CRecordView`, rufen Sie eine der Formen des Konstruktors initialisieren das Ansichtsobjekt und identifizieren die Dialogressource, auf denen die Sicht basiert.  
  
```  
explicit CRecordView(LPCTSTR lpszTemplateName);  
explicit CRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszTemplateName*  
 Enthält eine Null-terminierte Zeichenfolge, die den Namen des einer Dialogfeldvorlagen-Ressource ist.  
  
 *nIDTemplate*  
 Enthält die ID einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine Ganzzahl ohne Vorzeichen als Argument) identifizieren. Eine Ressource wird ID empfohlen.  
  
> [!NOTE]
>  Die abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. Rufen Sie im Konstruktor der abgeleiteten Klasse den Konstruktor `CRecordView::CRecordView` mit dem Ressourcennamen oder die ID als Argument, wie im folgenden Beispiel gezeigt.  
  
 **CRecordView::OnInitialUpdate** Aufrufe `UpdateData`, welche Aufrufe `DoDataExchange`. Diese ersten Aufruf der `DoDataExchange` verbindet `CRecordView` steuert (indirekt) zu `CRecordset` Felddatenmember von ClassWizard erstellt. Diese Datenmember können nicht erst verwendet werden, nach dem Aufruf der Basisklasse **CFormView::OnInitialUpdate** Memberfunktion.  
  
> [!NOTE]
>  Bei Verwendung von ClassWizard definiert der Assistent eine **Enum** Wert `CRecordView::IDD`, gibt es in der Klassendeklaration, und es in der Member-Initialisierungsliste des Konstruktors verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>  CRecordView::IsOnFirstRecord  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz des ersten Datensatzes im Recordset-Objekt, das diese Datensatzansicht zugeordnet ist.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Datensatz der erste Datensatz im Recordset ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich für das Schreiben von Ihren eigenen Implementierungen des Standard-befehlsupdatehandler von ClassWizard geschrieben.  
  
 Wenn der Benutzer auf den ersten Eintrag verschoben werden, deaktiviert das Framework jede Benutzeroberflächenobjekte, die Sie für die Umstellung auf das erste oder der vorherige Datensatz verfügen.  
  
##  <a name="isonlastrecord"></a>  CRecordView::IsOnLastRecord  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz der letzte Datensatz in das Recordset-Objekt, das diese Datensatzansicht zugeordnet ist.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Datensatz der letzte Datensatz in das Recordset ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich für das Schreiben von Ihren eigenen Implementierungen der standardmäßigen befehlsupdatehandler, die ClassWizard schreibt, um eine Benutzeroberfläche zum Navigieren zwischen Datensätzen zu unterstützen.  
  
> [!CAUTION]
>  Das Ergebnis dieser Funktion ist zuverlässig, mit dem Unterschied, dass die Ansicht das Ende des Recordsets nicht erkennen kann, bis der Benutzer hinaus verschoben wurde. Der Benutzer muss hinter dem letzten Datensatz verschieben, bevor die Datensatzansicht erkennen kann, müssen sie jede Benutzeroberflächenobjekte für das Verschieben in den nächsten oder letzten Datensatz deaktivieren. Wenn der Benutzer wird hinter dem letzten Datensatz verschoben, und klicken Sie dann zurück zum letzten Datensatz wechselt (oder davor), kann die Datensatzansicht Position des Benutzers im Recordset nachverfolgen und Benutzeroberflächenobjekte ordnungsgemäß deaktiviert. `IsOnLastRecord` auch nach einem Aufruf an die Implementierung-Funktion nicht zuverlässig ist `OnRecordLast`, welche behandelt die `ID_RECORD_LAST` Befehl oder `CRecordset::MoveLast`.  
  
##  <a name="ongetrecordset"></a>  CRecordView::OnGetRecordset  
 Gibt einen Zeiger auf die `CRecordset`-abgeleitetes Objekt der Datensatzansicht zugeordnet.  
  
```  
virtual CRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CRecordset`-abgeleitetes Objekt aus, wenn das Objekt erfolgreich erstellt; andernfalls wurde eine **NULL** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Erstellen oder einem Recordset-Objekt abrufen und einen Zeiger darauf zurückgeben. Wenn Sie die datensatzansichtsklasse mit ClassWizard deklarieren, schreibt der Assistent eine Standard-Außerkraftsetzung für Sie. ClassWizard die Standardimplementierung gibt den Recordsets Zeiger in der Datensatzansicht gespeichert werden, sofern vorhanden. Wenn nicht, die es einem Recordset-Objekt des Typs erstellt angegebenen mit ClassWizard und ruft seine `Open` Member Funktion, um öffnen Sie die Tabelle, oder führen Sie die Abfrage, und klicken Sie dann einen Zeiger auf das Objekt zurückgibt.  
  
 Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  CRecordView::OnMove  
 Rufen Sie diese Memberfunktion zum Wechseln zu einem anderen Datensatz des Recordsets und ihre Felder in die Steuerelemente der Datensatzansicht angezeigt.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDMoveCommand`  
 Einer der folgenden Werte Standardbefehls-ID:  
  
- `ID_RECORD_FIRST` Verschieben Sie auf den ersten Eintrag in das Recordset.  
  
- `ID_RECORD_LAST` Wechselt zur letzten Datensatz des Recordsets.  
  
- `ID_RECORD_NEXT` Verschieben Sie in den nächsten Datensatz in das Recordset.  
  
- `ID_RECORD_PREV` Wechseln Sie zum vorherigen Datensatz im Recordset.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verschiebung erfolgreich war; andernfalls 0, wenn die Anforderung zum Verschieben von verweigert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Ruft die entsprechende `Move` Memberfunktion der `CRecordset` Objekt, das mit der Datensatzansicht zugeordnet.  
  
 Standardmäßig `OnMove` den aktuellen Datensatz in der Datenquelle aktualisiert, wenn der Benutzer in der Datensatzansicht geändert hat.  
  
 Der Anwendungs-Assistent erstellt eine Menüressource mit ersten, letzten Datensatzes, nächsten Datensatz, und vorherigen Datensatz Menüelemente an. Wenn Sie die Option andockbare Symbolleiste auswählen, erstellt der Anwendungs-Assistent auch eine Symbolleiste mit Schaltflächen, die auf diese Befehle entspricht.  
  
 Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, weiterhin die Datensatzansicht den letzten Datensatz anzuzeigen. Wenn Sie nach dem ersten Datensatz rückwärts verschieben, können Sie weiterhin die Datensatzansicht des ersten Datensatzes angezeigt.  
  
> [!CAUTION]
>  Aufrufen von `OnMove` löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie die entsprechende Schnittstelle Update Handlerfunktion – `OnUpdateRecordFirst`, `OnUpdateRecordLast`, `OnUpdateRecordNext`, oder `OnUpdateRecordPrev` – vor den entsprechenden Verschiebevorgang, um zu bestimmen, ob das Recordset alle Datensätze aufweist.  
  
## <a name="see-also"></a>Siehe auch  
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)
