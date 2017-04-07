---
title: CRecordView-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
- AFXDB/CRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CRecordView class
- ODBC recordsets, viewing records
- records, viewing ODBC
- views, ODBC
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 04ff47900037dcbaa12e2cba2c9a3e84caf54a69
ms.lasthandoff: 02/24/2017

---
# <a name="crecordview-class"></a>CRecordView-Klasse
Eine Sicht, die Datenbankdatensätze in Steuerelementen anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordView::CRecordView](#crecordview)|Erstellt ein `CRecordView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|Gibt einen Wert ungleich NULL, wenn der aktuelle Datensatz des ersten Datensatzes im Recordset-Objekt zugeordnet ist.|  
|[CRecordView::IsOnLastRecord](#isonlastrecord)|Gibt einen Wert ungleich NULL, wenn der aktuelle Datensatz der letzte Datensatz im Recordset-Objekt zugeordnet ist.|  
|[CRecordView::OnGetRecordset](#ongetrecordset)|Gibt einen Zeiger auf ein Objekt einer abgeleiteten Klasse `CRecordset`. Klassen-Assistent überschreibt diese Funktion für Sie und erstellt das Recordset, bei Bedarf.|  
|[CRecordView::OnMove](#onmove)||  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordView::OnMove](#onmove)|Wenn der aktuelle Datensatz geändert hat, wird in der Datenquelle aktualisiert, und wechselt dann zum angegebenen Datensatz (nächsten, vorherigen, ersten oder letzten).|  
  
## <a name="remarks"></a>Hinweise  
 Die Ansicht ist eine direkte Verbindung zum Formularansicht ein `CRecordset` Objekt. Die Ansicht einer Dialogfeldvorlagen-Ressource erstellt wird, und zeigt die Felder an die `CRecordset` Objekt in der Dialogfeldvorlagen-Steuerelementen. Das `CRecordView` -Objekt verwendet den Dialogdatenaustausch (DDX) und Datensatzfeldaustausch (RFX) automatisiert die Verschiebung von Daten zwischen den Steuerelementen auf dem Formular und die Felder des Recordset-Objekts. `CRecordView`liefert auch eine Standardimplementierung für einen Wechsel zum ersten, nächsten, vorherigen oder letzten Datensatz und eine Schnittstelle zum Aktualisieren der aktuell angezeigten Datensatzes.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Die gängigste Methode zum Erstellen der Datensatzansicht ist mit dem Assistenten für die Anwendung. Dann Anwendung-Assistent erstellt die datensatzansichtsklasse und seiner zugehörigen Recordset-Klasse als Teil Ihrer startanwendung Skelett. Wenn Sie die datensatzansichtsklasse mit dem Assistenten zum erstellen möchten, können Sie es später mit dem Klassen-Assistenten erstellen. Der Assistent Ansatz ist einfacher, wenn Sie lediglich ein einzelnes Formular. Klassen-Assistenten können Sie die eine Datensatzansicht später im Entwicklungsprozess verwenden möchten. Klassen-Assistent zum Erstellen einer Datensatzansicht und ein Recordset getrennt, und schließen sie dann mithilfe der flexibelste Ansatz ist, denn es Ihnen mehr Kontrolle ermöglicht bei der Benennung der Recordset-Klasse und deren. H /. CPP-Dateien. Dieser Ansatz lässt auch mehrere Datensatzansichten in der gleichen Recordsetklasse.  
  
 Um Endbenutzer zum Verschieben von Datensatz zu Datensatz in der Datensatzansicht zu erleichtern, erstellt der Assistent Menü-(und optional) zum Verschieben von Ressourcen zum ersten, nächsten, vorherigen oder letzten Datensatz. Wenn Sie eine Datensatzansichts-Klasse mit dem Klassen-Assistenten erstellen, müssen Sie diese Ressourcen selbst mit dem Menü und Bitmap Editoren erstellen.  
  
 Informationen über die standardmäßige Implementierung für das Verschieben von Datensatz zu Datensatz finden Sie unter `IsOnFirstRecord` und `IsOnLastRecord` und im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView`behält Verfolgen der Position des Benutzers im Recordset, damit die Datensatzansicht die Benutzeroberfläche aktualisieren kann. Wenn der Benutzer an beiden Enden des Recordsets verschiebt, deaktiviert die Datensatzansicht Benutzeroberflächenobjekte – z. B. Menüelemente und Symbolleisten-Schaltflächen – für das Verschieben von weiter in die gleiche Richtung.  
  
 Weitere Informationen zu deklarieren und Verwenden der Datensatzansicht und ein Recordset-Klassen finden Sie unter "Entwerfen und Erstellen einer Datensatzansicht" im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md). Weitere Informationen wie von Datensatzansichten und deren Verwendung finden Sie im Artikel [Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="crecordview"></a>CRecordView::CRecordView  
 Wenn Sie ein Objekt eines Typs erstellen von abgeleiteten `CRecordView`, rufen Sie eine Form des Konstruktors initialisieren das Ansichtsobjekt und identifizieren die Dialogfeldressource, auf denen die Sicht basiert.  
  
```  
explicit CRecordView(LPCTSTR lpszTemplateName);  
explicit CRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine auf Null endende Zeichenfolge, die den Namen des einer Dialogfeldvorlagen-Ressource ist.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder die Ressource anhand des Namens (übergeben Sie eine Zeichenfolge als Argument an den Konstruktor) oder nach seiner ID (übergeben Sie eine ganze Zahl als Argument) identifizieren. Eine Ressource ist ID empfohlen.  
  
> [!NOTE]
>  Die abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. Rufen Sie im Konstruktor der abgeleiteten Klasse die `CRecordView::CRecordView` mit dem Ressourcennamen oder die ID als Argument, wie im folgenden Beispiel gezeigt.  
  
 **CRecordView::OnInitialUpdate** Aufrufe `UpdateData`, welche `DoDataExchange`. Diese ersten Aufruf der `DoDataExchange` verbindet `CRecordView` (indirekt) steuert `CRecordset` Felddatenmember vom Klassen-Assistenten erstellt. Diese Datenmember können nicht erst verwendet werden, nach dem Aufruf der Basisklasse **CFormView::OnInitialUpdate** Member-Funktion.  
  
> [!NOTE]
>  Wenn Sie Klassen-Assistenten verwenden, wird der Assistent definiert ein `enum` Wert `CRecordView::IDD`, gibt es in der Klassendeklaration, und in der Memberinitialisierungsliste des Konstruktors verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#32;](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>CRecordView::IsOnFirstRecord  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz des ersten Datensatzes im Recordset-Objekt, das dieser Eintrag Ansicht zugeordnet ist.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Datensatz der erste Datensatz im Recordset ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist hilfreich beim Schreiben Ihre eigenen Implementierungen von Standard-befehlsupdatehandler von ClassWizard geschrieben.  
  
 Wenn der Benutzer auf den ersten Datensatz verschoben wird, deaktiviert das Framework alle Benutzeroberflächenobjekte haben Sie für die Umstellung auf die erste oder vorherigen Datensatz.  
  
##  <a name="isonlastrecord"></a>CRecordView::IsOnLastRecord  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz der letzte Datensatz im Recordset-Objekt, das dieser Eintrag Ansicht zugeordnet ist.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der aktuelle Datensatz der letzte Datensatz im Recordset ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist hilfreich beim Schreiben eigener Implementierungen der standardmäßigen befehlsupdatehandler, die Klassen-Assistent schreibt, um eine Benutzeroberfläche für das Verschieben von Datensatz zu Datensatz zu unterstützen.  
  
> [!CAUTION]
>  Das Ergebnis dieser Funktion ist zuverlässig, abgesehen davon, dass die Ansicht das Ende des Recordset-Objekts nicht erkennen kann, bis der Benutzer, fügen Sie sie gewechselt hat. Der Benutzer muss hinter dem letzten Datensatz wechseln, bevor die Datensatzansicht erkennen kann, müssen sie alle Benutzeroberflächenobjekte für das Verschieben in den nächsten oder letzten Datensatz deaktivieren. Wenn der Benutzer hinter dem letzten Datensatz bewegt und dann wieder mit dem letzten Datensatz (oder davor), kann die Datensatzansicht Verfolgen der Position des Benutzers im Recordset und Benutzeroberflächenobjekte ordnungsgemäß deaktiviert. `IsOnLastRecord`wird auch nach einem Aufruf der Funktion Implementierung unzuverlässig **OnRecordLast**, welche behandelt die `ID_RECORD_LAST` Befehl oder `CRecordset::MoveLast`.  
  
##  <a name="ongetrecordset"></a>CRecordView::OnGetRecordset  
 Gibt einen Zeiger auf die `CRecordset`-abgeleitete Objekt, das mit der Datensatzansicht zugeordnet.  
  
```  
virtual CRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CRecordset`-abgeleitetes Objekt, wenn das Objekt erfolgreich erstellt; andernfalls wurde ein **NULL** Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Memberfunktion zum Erstellen oder Abrufen eines Recordsetobjekts und einen Zeiger darauf zurückgeben. Wenn Sie Datensatzansichts-Klasse mit dem Klassen-Assistenten deklariert haben, schreibt der Assistent eine Standard-Außerkraftsetzung für Sie. Die standardmäßige Implementierung des Klassen-Assistent gibt den Recordset-Zeiger in der Datensatzansicht gespeichert, sofern vorhanden. Wenn nicht, er einem Recordset-Objekt des Typs erstellt angegebenen mit dem Klassen-Assistenten und ruft seine **öffnen** Element funktioniert, öffnen Sie die Tabelle, oder führen die Abfrage und gibt dann einen Zeiger auf das Objekt.  
  
 Weitere Informationen und Beispiele finden Sie im Artikel [Datensatzansichten: Verwenden einer Datensatzansicht](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>CRecordView::OnMove  
 Rufen Sie diese Memberfunktion zum Wechseln zu einem anderen Datensatz im Recordset, und ihre Felder den Steuerelementen der Datensatzansicht angezeigt.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDMoveCommand`  
 Einer der folgenden Standardbefehls-ID-Werte:  
  
- `ID_RECORD_FIRST`Verschieben Sie auf den ersten Datensatz im Recordset.  
  
- `ID_RECORD_LAST`Wechselt zur letzten Datensatz im Recordset.  
  
- `ID_RECORD_NEXT`Wechseln Sie zum nächsten Datensatz im Recordset.  
  
- `ID_RECORD_PREV`Wechseln Sie zum vorherigen Datensatz im Recordset.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verschiebung erfolgreich war; andernfalls 0, wenn die Move-Anforderung verweigert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft die entsprechende **verschieben** Memberfunktion der `CRecordset` Objekt, das mit der Datensatzansicht zugeordnet.  
  
 In der Standardeinstellung `OnMove` den aktuellen Datensatz in der Datenquelle aktualisiert, wenn der Benutzer in der Datensatzansicht geändert hat.  
  
 Der Assistent erstellt eine Menüressource mit ersten, letzten Datensatz, nächsten Datensatz, und vorherigen Datensatz Menüelemente. Wenn Sie die Option andockbare Symbolleiste auswählen, erstellt der Assistent auch eine Symbolleiste mit Schaltflächen für diese Befehle.  
  
 Wenn Sie hinter dem letzten Datensatz im Recordset verschieben, wird die Datensatzansicht weiterhin den letzten Datensatz angezeigt. Wenn Sie nach dem ersten Datensatz rückwärts verschieben, können Sie weiterhin die Datensatzansicht des ersten Datensatzes angezeigt.  
  
> [!CAUTION]
>  Aufrufen von `OnMove` löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. Rufen Sie die entsprechende Schnittstelle Update Handlerfunktion – **OnUpdateRecordFirst**, **OnUpdateRecordLast**, **OnUpdateRecordNext**, oder **OnUpdateRecordPrev** , verschieben Sie vor den entsprechenden Vorgang zu bestimmen, ob das Recordset alle Datensätze vorhanden sind.  
  
## <a name="see-also"></a>Siehe auch  
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)

