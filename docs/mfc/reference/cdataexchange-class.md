---
title: CDataExchange-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: 0e7a9d429acb1acd72942e5f10ac0815232ddc69
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776309"
---
# <a name="cdataexchange-class"></a>CDataExchange-Klasse

Unterstützt die Routinen für den Dialogdatenaustausch (Dialog Data Exchange, DDX) und die Dialogfelddatenvalidierung (Dialog Data Validation, DDV), die von den Microsoft Foundation-Klassen verwendet werden.

## <a name="syntax"></a>Syntax

```
class CDataExchange
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDataExchange::CDataExchange](#cdataexchange)|Erstellt ein `CDataExchange`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDataExchange::Fail](#fail)|Wird aufgerufen, wenn die Validierung fehlschlägt. Setzt den Fokus auf das vorherige Steuerelement aus, und löst eine Ausnahme aus.|
|[CDataExchange::PrepareCtrl](#preparectrl)|Bereitet das angegebene Steuerelement für den Datenaustausch oder Validierung an. Verwenden Sie für Nonedit Steuerelemente.|
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Bereitet das angegebene Edit-Steuerelement für den Datenaustausch oder Validierung vor.|
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Bereitet das angegebene OLE-Steuerelement für den Datenaustausch oder Validierung an. Verwenden Sie für Nonedit Steuerelemente.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Für die Richtung des DDX- und DDV-Flag.|
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Das Dialogfeld oder Fenster, in dem der Datenaustausch, erfolgt.|

## <a name="remarks"></a>Hinweise

`CDataExchange` eine Basisklasse keinen.

Verwenden Sie diese Klasse aus, wenn Sie für benutzerdefinierte Datentypen oder Steuerelemente, Data Exchange-Routinen schreiben, oder wenn Sie Ihre eigenen datenvalidierungsroutine schreiben. Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfelder](../../mfc/dialog-boxes.md).

Ein `CDataExchange` Objekt stellt die Kontextinformationen, die erforderlich sind, für die DDX- und DDV zu platzieren. Das Flag *M_bSaveAndValidate* ist "false", wenn DDX zum Füllen die Anfangswerte der Dialogfeld-Steuerelemente von Datenmembern verwendet wird. Das Flag *M_bSaveAndValidate* ist wahr, wenn DDX verwendet wird, die aktuellen Werte der Dialogfeld-Steuerelemente in der Datenmember und wenn DDV verwendet wird, zum Überprüfen der Datenwerte festgelegt. Wenn die DDV-Validierung fehlschlägt, wird der DDV-Prozedur ein Meldungsfeld, erläutern die Eingabefehler angezeigt. Die Prozedur DDV ruft dann `Fail` den Fokus auf das problematische Steuerelement zurückgesetzt, und löst eine Ausnahme aus, um den Überprüfungsprozess zu beenden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CDataExchange`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange

Rufen Sie diese Memberfunktion zum Erstellen einer `CDataExchange` Objekt.

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>Parameter

*pDlgWnd*<br/>
Ein Zeiger auf das übergeordnete Fenster, das das Steuerelement enthält. Dies ist normalerweise ein [CDialog](../../mfc/reference/cdialog-class.md)-abgeleitetes Objekt.

*bSaveAndValidate*<br/>
True gibt an, dieses Objekt Daten überprüft und schreibt dann Daten aus den Steuerelementen auf die Member. False gibt an, wird dieses Objekt an Steuerelemente Daten aus Elementen verschieben.

### <a name="remarks"></a>Hinweise

Erstellen einer `CDataExchange` Objekt selbst zum Speichern von zusätzlichen Informationen im Exchange-Objekt an des Fensters des übergeben [Ddx_managedcontrol](../../mfc/reference/cwnd-class.md#dodataexchange) Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

##  <a name="fail"></a>  CDataExchange::Fail

Das Framework ruft diese Memberfunktion auf, wenn ein Dialogfeld Data Validation, (DDV)-Vorgang fehlschlägt.

```
void Fail();
```

### <a name="remarks"></a>Hinweise

`Fail` stellt Sie den Fokus und Auswahl an das Steuerelement, dessen Überprüfung ist fehlgeschlagen (wenn ein Steuerelement wiederherstellen) wieder her. `Fail` Klicken Sie dann löst eine Ausnahme vom Typ [CUserException](../../mfc/reference/cuserexception-class.md) um die Überprüfung zu beenden. Die Ausnahme bewirkt, dass ein Meldungsfeld, einer Beschreibung des Fehlers, der angezeigt werden. DDV-Überprüfung ein Fehler aufgetreten ist, kann der Benutzer Daten in der betreffenden Steuerelement erneut eingeben.

Implementierer von benutzerdefinierten DDV-Routinen können Aufrufen `Fail` in ihren Routinen, die bei einem Überprüfungsfehler fehlschlägt.

Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).

##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate

Dieses Flag gibt die Richtung eines Datenvorgangs Dialogdatenaustausch (DDX) Dialogfeld an.

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>Hinweise

Das Flag ungleich NULL ist. wenn die `CDataExchange` Objekt wird verwendet, um das Verschieben von Daten aus der Dialogfeld-Steuerelemente zum Dialogfeld-Klassendatenmember, nachdem der Benutzer die Steuerelemente bearbeitet. Das Flag ist 0 (null), wenn das Objekt zum Initialisieren der Dialogfeld-Steuerelemente aus der Datenmember der Dialogfeld-Klasse verwendet wird.

Das Flag ist auch beim Validieren von Dialogfelddaten (DDV) ungleich NULL.

Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).

##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd

Enthält einen Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) Objekt, für welche Dialog Daten Dialogdatenaustausch (DDX) oder der Überprüfung (DDV) stattfindet.

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>Hinweise

Dieses Objekt stellt normalerweise eine [CDialog](../../mfc/reference/cdialog-class.md) Objekt. This-Zeiger können Implementierungen von benutzerdefinierten DDX oder DDV-Routinen erhalten Zugriff auf das Dialogfeld, das die Steuerelemente enthält, die auf dem sie arbeiten.

Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).

##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl

Das Framework ruft diese Member-Funktion, um das angegebene Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorzubereiten.

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>Parameter

*nIDC*<br/>
Die ID des Steuerelements für DDX oder DDV vorbereitet werden.

### <a name="return-value"></a>Rückgabewert

Das HWND des Steuerelements für den DDX oder DDV vorbereitet wird.

### <a name="remarks"></a>Hinweise

Verwenden Sie [PrepareEditCtrl](#prepareeditctrl) für Bearbeitungssteuerelemente; verwenden Sie stattdessen diese Member-Funktion für alle anderen Steuerelemente.

Vorbereitung umfasst das Speichern von HWND des Steuerelements, in der `CDataExchange` Klasse. Das Framework verwendet dieses Handle, den Fokus auf das zuvor fokussierte Steuerelement bei einem Ausfall DDX oder DDV wiederherzustellen.

Implementierer von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareCtrl` für alle nicht-Edit-Steuerelemente für die sie Austauschen von Daten über DDX oder Überprüfen von Daten über DDV.

Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).

##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl

Das Framework ruft diese Member-Funktion, um das angegebene Bearbeitungssteuerelement für Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorzubereiten.

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>Parameter

*nIDC*<br/>
Die ID des Bearbeitungssteuerelements für DDX oder DDV vorbereitet werden.

### <a name="return-value"></a>Rückgabewert

Das HWND des Bearbeitungssteuerelements für DDX oder DDV vorbereitet wird.

### <a name="remarks"></a>Hinweise

Verwendung [PrepareCtrl](#preparectrl) stattdessen für alle nicht-Edit-Steuerelemente.

Vorbereitung umfasst zwei Schritte. Zuerst `PrepareEditCtrl` speichert HWND des Steuerelements, in der `CDataExchange` Klasse. Das Framework verwendet dieses Handle, den Fokus auf das zuvor fokussierte Steuerelement bei einem Ausfall DDX oder DDV wiederherzustellen. Zweitens `PrepareEditCtrl` setzt ein Flag in der `CDataExchange` Klasse an, dass das Steuerelement, dessen Daten ausgetauscht werden, oder überprüft ein Bearbeitungssteuerelement ist.

Implementierer von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareEditCtrl` für alle Steuerelemente für die sie Austauschen von Daten über DDX oder Überprüfen von Daten über DDV zu bearbeiten.

Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).

##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl

Das Framework ruft diese Member-Funktion, um das angegebene OLE-Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorzubereiten.

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>Parameter

*nIDC*<br/>
Die ID des OLE-Steuerelements für DDX oder DDV vorbereitet werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Website des OLE-Steuerelements.

### <a name="remarks"></a>Hinweise

Verwendung [PrepareEditCtrl](#prepareeditctrl) stattdessen für Bearbeitungssteuerelemente oder [PrepareCtrl](#preparectrl) für alle anderen nicht-OLE-Steuerelemente.

Implementierer von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareOleCtrl` für alle OLE-Steuerelemente für die sie Austauschen von Daten über DDX oder Überprüfen von Daten über DDV.

Weitere Informationen zu Ihren eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
