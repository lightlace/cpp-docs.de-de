---
title: CDaoRecordView-Klasse | Microsoft Docs
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
ms.openlocfilehash: 07dc58332bc99cb01e9b6567eafe2cb5b96f1b9c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368949"
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
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|Gibt einen Wert ungleich NULL, wenn der aktuelle Datensatz der erste Datensatz im zugehörigen Recordset ist.|  
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|Gibt einen Wert ungleich NULL, wenn der aktuelle Datensatz der letzte Datensatz in der zugehörigen Recordset ist.|  
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|Gibt einen Zeiger auf ein Objekt einer Klasse abgeleitet `CDaoRecordset`. Klassen-Assistent überschreibt diese Funktion für Sie und erstellt das Recordset, bei Bedarf.|  
|[CDaoRecordView::OnMove](#onmove)|Wenn der aktuelle Datensatz geändert hat, wird für die Datenquelle aktualisiert, und klicken Sie dann wechselt zum angegebenen Datensatz (nächsten, vorherigen, ersten oder letzten).|  
  
## <a name="remarks"></a>Hinweise  
 Die Ansicht ist eine Formularansicht können Sie eine direkte Verbindung zum ein `CDaoRecordset` Objekt. Die Sicht aus einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder der `CDaoRecordset` Objekt in der Dialogfeldvorlage-Steuerelementen. Die `CDaoRecordView` Objekt verwendet Dialogdatenaustausch (DDX) und DAO-Datensatzfeldaustausch (DFX), um die Verschiebung von Daten zwischen den Steuerelementen im Formular und die Felder des Recordsets zu automatisieren. `CDaoRecordView` Außerdem stellt eine Standardimplementierung für das Verschieben von mit dem ersten nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren des Datensatzes in der Ansicht.  
  
> [!NOTE]
>  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können dennoch den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen; DAO-Klassen bieten im Allgemeinen überlegene Funktionen auf, da sie das Microsoft Jet-Datenbankmodul verwenden.  
  
 Die gängigste Methode zum Erstellen der Datensatzansicht ist mit dem Anwendungs-Assistenten. Die Anwendungs-Assistent erstellt die datensatzansichtsklasse und seiner zugehörigen Recordset-Klasse als Teil Ihrer Anwendung das Gerüst eines Starter.  
  
 Wenn Sie einfach ein einzelnes Formular benötigen, ist der Anwendungs-Assistent-Ansatz vereinfacht. Klassen-Assistenten können Sie die eine Datensatzansicht später im Entwicklungsprozess verwenden möchten. Wenn Sie die datensatzansichtsklasse mit dem Assistenten zum Erstellen, können Sie es später mit ClassWizard erstellen. Die flexibelste Herangehensweise wird mithilfe der Klassen-Assistent zum Erstellen einer Datensatzansicht und ein Recordset getrennt und dann eine Verbindung herstellen, denn es Ihnen mehr Kontrolle ermöglicht bei der Benennung der Recordset-Klasse und ihre. H /. CPP-Dateien. Dieser Ansatz können auch mehrere Datensatzansichten in der gleichen Recordsetklasse verfügen.  
  
 Um Möglichkeit zum Verschieben von Datensatz zu Datensatz in der Datensatzansicht zu erleichtern, erstellt der Assistent Anwendung Menü-(und optional) zum Verschieben von Ressourcen mit dem ersten nächsten, vorherigen oder letzten Datensatz. Wenn Sie eine datensatzansichtsklasse mit ClassWizard erstellen, müssen Sie diese Ressourcen selbst mit dem Menü und Bitmap-Editor erstellen.  
  
 Informationen über die standardmäßige Implementierung für das Verschieben von Datensatz zu Datensatz finden Sie unter `IsOnFirstRecord` und `IsOnLastRecord` und im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md), die gelten für beide `CRecordView` und `CDaoRecordView`.  
  
 `CDaoRecordView` behält den Überblick über die Position des Benutzers im Recordset, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann. Wenn der Benutzer an beiden Enden des Recordsets verschoben wird, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte – z. B. Menüelemente und Symbolleisten-Schaltflächen – zum Verschieben in die gleiche Richtung weiter.  
  
 Weitere Informationen zu deklarieren und Verwenden der Datensatzansicht und Recordset-Klassen, finden Sie unter "Entwerfen und Erstellen einer Datensatzansicht" im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md). Weitere Informationen wie von Datensatzansichten und deren Verwendung finden Sie im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md). Alle Artikel, die oben genannten gelten für beide `CRecordView` und `CDaoRecordView`.  
  
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
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `CDaoRecordView`, rufen Sie eine der Formen des Konstruktors initialisieren das Ansichtsobjekt und identifizieren die Dialogressource, auf denen die Sicht basiert.  
  
```  
explicit CDaoRecordView(LPCTSTR lpszTemplateName);  
explicit CDaoRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine Null-terminierte Zeichenfolge, die den Namen des einer Dialogfeldvorlagen-Ressource ist.  
  
 `nIDTemplate`  
 Enthält die ID einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine Ganzzahl ohne Vorzeichen als Argument) identifizieren. Eine Ressource wird ID empfohlen.  
  
> [!NOTE]
>  Die abgeleitete Klasse muss einen eigenen Konstruktor angeben. Rufen Sie im Konstruktor der abgeleiteten Klasse den Konstruktor `CDaoRecordView::CDaoRecordView` mit dem Ressourcennamen oder die ID als Argument.  
  
 **CDaoRecordView::OnInitialUpdate** Aufrufe `CWnd::UpdateData`, welche Aufrufe `CWnd::DoDataExchange`. Diese ersten Aufruf der `DoDataExchange` verbindet `CDaoRecordView` steuert (indirekt) zu `CDaoRecordset` Felddatenmember von ClassWizard erstellt. Diese Datenmember können nicht erst verwendet werden, nach dem Aufruf der Basisklasse **CFormView::OnInitialUpdate** Memberfunktion.  
  
> [!NOTE]
>  Bei Verwendung von ClassWizard definiert der Assistent eine `enum` Wert `CDaoRecordView::IDD` in der Deklaration der Klasse und verwendet, die sie bei der Memberinitialisierung auflisten, für den Konstruktor.  
  
 [!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>  CDaoRecordView::IsOnFirstRecord  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz des ersten Datensatzes im Recordset-Objekt, das diese Datensatzansicht zugeordnet ist.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Datensatz der erste Datensatz im Recordset ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich für das Schreiben von Ihren eigenen Implementierungen der standardmäßigen befehlsupdatehandler von ClassWizard geschrieben.  
  
 Wenn der Benutzer auf den ersten Eintrag verschoben werden, haben mit der Benutzeroberfläche (z. B. Menüelemente oder Symbolleisten-Schaltflächen)-Objekte Framework deaktiviert für die Umstellung auf das erste oder der vorherige Datensatz.  
  
##  <a name="isonlastrecord"></a>  CDaoRecordView::IsOnLastRecord  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz der letzte Datensatz in das Recordset-Objekt, das diese Datensatzansicht zugeordnet ist.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Datensatz der letzte Datensatz in das Recordset ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich für das Schreiben von Ihren eigenen Implementierungen der standardmäßigen befehlsupdatehandler, die ClassWizard schreibt, um eine Benutzeroberfläche zum Navigieren zwischen Datensätzen zu unterstützen.  
  
> [!CAUTION]
>  Das Ergebnis dieser Funktion ist zuverlässig, mit dem Unterschied, dass die Ansicht möglicherweise nicht erkennen Sie das Ende des Recordset-Objekts, bis der Benutzer hinaus verschoben wurde. Der Benutzer möglicherweise hinter dem letzten Datensatz zu verschieben, bevor die Datensatzansicht erkennen kann, müssen sie jede Benutzeroberflächenobjekte für das Verschieben in den nächsten oder letzten Datensatz deaktivieren. Wenn der Benutzer wird hinter dem letzten Datensatz verschoben, und klicken Sie dann zurück zum letzten Datensatz wechselt (oder davor), kann die Datensatzansicht Position des Benutzers im Recordset nachverfolgen und Benutzeroberflächenobjekte ordnungsgemäß deaktiviert.  
  
##  <a name="ongetrecordset"></a>  CDaoRecordView::OnGetRecordset  
 Gibt einen Zeiger auf die `CDaoRecordset`-abgeleitetes Objekt der Datensatzansicht zugeordnet.  
  
```  
virtual CDaoRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CDaoRecordset`-abgeleitetes Objekt aus, wenn das Objekt erfolgreich erstellt; andernfalls wurde eine **NULL** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Erstellen oder einem Recordset-Objekt abrufen und einen Zeiger darauf zurückgeben. Wenn Sie die datensatzansichtsklasse mit ClassWizard deklarieren, schreibt der Assistent eine Standard-Außerkraftsetzung für Sie. ClassWizard die Standardimplementierung gibt den Recordsets Zeiger in der Datensatzansicht gespeichert werden, sofern vorhanden. Wenn nicht, die es einem Recordset-Objekt des Typs erstellt angegebenen mit ClassWizard und ruft seine **öffnen** Member Funktion, um öffnen Sie die Tabelle, oder führen Sie die Abfrage, und klicken Sie dann einen Zeiger auf das Objekt zurückgibt.  
  
 Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>  CDaoRecordView::OnMove  
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
 Die Standardimplementierung Ruft die entsprechenden Move-Memberfunktion von der `CDaoRecordset` Objekt, das mit der Datensatzansicht zugeordnet.  
  
 Standardmäßig `OnMove` den aktuellen Datensatz in der Datenquelle aktualisiert, wenn der Benutzer in der Datensatzansicht geändert hat.  
  
 Der Anwendungs-Assistent erstellt eine Menüressource mit ersten, letzten Datensatzes, nächsten Datensatz, und vorherigen Datensatz Menüelemente an. Wenn Sie die erste Symbolleiste-Option auswählen, erstellt der Anwendungs-Assistent auch eine Symbolleiste mit Schaltflächen, die auf diese Befehle entspricht.  
  
 Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, weiterhin die Datensatzansicht den letzten Datensatz anzuzeigen. Wenn Sie nach dem ersten Datensatz rückwärts verschieben, können Sie weiterhin die Datensatzansicht des ersten Datensatzes angezeigt.  
  
> [!CAUTION]
>  Aufrufen von `OnMove` löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie die entsprechende Schnittstelle Update Handlerfunktion – **OnUpdateRecordFirst**, **OnUpdateRecordLast**, **OnUpdateRecordNext**, oder  **OnUpdateRecordPrev** – vor den entsprechenden Verschiebevorgang, um zu bestimmen, ob das Recordset alle Datensätze aufweist.  
  
## <a name="see-also"></a>Siehe auch  
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)
