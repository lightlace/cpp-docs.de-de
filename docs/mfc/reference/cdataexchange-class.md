---
title: CDataExchange-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03d68359d075efd72a1bf1907daa71e74110fa28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CDataExchange::Fail](#fail)|Wird aufgerufen, wenn die Validierung fehlschlägt. Setzt den Fokus auf das vorherige Steuerelement zurück und löst eine Ausnahme aus.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|Bereitet das angegebene Steuerelement für den Datenaustausch oder Validierung vor. Verwenden Sie für Nonedit-Steuerelemente.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Bereitet das angegebene Bearbeitungssteuerelement für den Datenaustausch oder Überprüfung.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Bereitet das angegebene OLE-Steuerelement für den Datenaustausch oder Überprüfung vor. Verwenden Sie für Nonedit-Steuerelemente.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Flag für die Richtung des DDX- und DDV.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Das Dialogfeld oder Fenster, in dem Datenaustausch, findet.|  
  
## <a name="remarks"></a>Hinweise  
 `CDataExchange` eine Basisklasse verfügt nicht über.  
  
 Verwenden Sie diese Klasse aus, wenn Sie Daten Exchange Routinen für benutzerdefinierte Datentypen oder Steuerelemente, schreiben oder wenn Sie eine eigene datenvalidierungsroutine schreiben. Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfelder](../../mfc/dialog-boxes.md).  
  
 Ein `CDataExchange` Objekt stellt die Kontextinformationen für DDX- und DDV auszuführenden platzieren erforderlich. Das Flag `m_bSaveAndValidate` ist **"false"** Wenn DDX füllen die Anfangswerte für Dialogfeld-Steuerelemente aus Datenmember verwendet wird. Das Flag `m_bSaveAndValidate` ist **"true"** Wenn DDX verwendet wird, legen Sie die aktuellen Werte der Dialogfeld-Steuerelemente in Datenmember und wenn DDV verwendet wird, um die Datenwerte zu überprüfen. Wenn die DDV-Überprüfung ein Fehler auftritt, wird die DDV-Prozedur ein Meldungsfeld erläutern die Eingabefehler angezeigt. Ruft die Prozedur DDV dann **fehlschlagen** den Fokus auf das problematische Steuerelement zurückgesetzt und löst eine Ausnahme aus, um die Überprüfung abzubrechen.  
  
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
 *pDlgWnd*  
 Ein Zeiger auf das übergeordnete Fenster, das das Steuerelement enthält. Dies ist normalerweise eine [CDialog](../../mfc/reference/cdialog-class.md)-abgeleitetes Objekt.  
  
 `bSaveAndValidate`  
 Wenn **"true"**, dieses Objekt Daten überprüft und dann auf die Mitglieder können Daten aus den Steuerelementen geschrieben. Wenn **"false"**, dieses Objekt wird Daten von Mitgliedern zu Steuerelementen bewegt.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CDataExchange` Objekt zum Speichern von zusätzlichen Informationen in der Exchange-Datenobjekt Übergabe an des Fensters selbst [Ddx_managedcontrol](../../mfc/reference/cwnd-class.md#dodataexchange) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>  CDataExchange::Fail  
 Das Framework ruft diese Memberfunktion auf, wenn ein Dialogfeld Data Validation (DDV)-Vorgang fehlschlägt.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>Hinweise  
 **Fehlschlagen** stellt den Fokus und Auswahl an das Steuerelement, dessen Überprüfung ist fehlgeschlagen (wenn ein Steuerelement zum Wiederherstellen) wieder her. **Fehlschlagen** löst dann eine Ausnahme vom Typ [CUserException](../../mfc/reference/cuserexception-class.md) zum Beenden des Überprüfungsprozesses. Die Ausnahme bewirkt, dass ein Meldungsfeld, einer Beschreibung des Fehlers angezeigt werden. Wenn DDV-Validierung fehlgeschlagen ist, kann der Benutzer Daten im betreffenden Steuerelement erneut ein.  
  
 In einer Implementierung der benutzerdefinierten DDV-Routinen können Aufrufen **fehlschlagen** aus ihren Routinen, die bei einem Überprüfungsfehler fehlschlägt.  
  
 Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate  
 Dieses Flag gibt die Richtung von einem Dialogfeld Dialogdatenaustausch (DDX) Datenvorgang an.  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Flag ist ungleich NULL Wenn die `CDataExchange` Objekt wird verwendet, um Daten aus dem Dialogfeld-Steuerelemente in Dialogfeld Klassendatenmember verschieben, nachdem der Benutzer die Steuerelemente bearbeitet. Das Flag ist 0 (null), wenn das Objekt zum Initialisieren der Dialogfeld-Steuerelemente aus der Dialogfeldklasse Datenmember verwendet wird.  
  
 Das Flag ist außerdem bei Validieren von Dialogfelddaten (DDV) ungleich NULL ist.  
  
 Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd  
 Enthält einen Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) Objekt, für welche Dialog Daten Dialogdatenaustausch (DDX) oder Überprüfung (DDV) ist, die stattfinden.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt stellt normalerweise eine [CDialog](../../mfc/reference/cdialog-class.md) Objekt. This-Zeiger können in einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen erhalten Zugriff auf das Dialogfeld, das die Steuerelemente enthält, die sie für ausgeführt werden.  
  
 Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl  
 Das Framework ruft diese Memberfunktion, um das angegebene Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorzubereiten.  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDC`  
 Die ID des Steuerelements für DDX oder DDV vorbereitet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HWND` des Steuerelements für DDX oder DDV vorbereitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie [PrepareEditCtrl](#prepareeditctrl) für Bearbeitungssteuerelemente; verwenden Sie stattdessen diese Memberfunktion für alle anderen Steuerelemente.  
  
 Vorbereitung umfasst das Speichern des Steuerelements `HWND` in die `CDataExchange` Klasse. Das Framework verwendet dieses Handle, um den Fokus auf das Steuerelement zuvor mit Fokus im Fall eines Fehlers DDX oder DDV wiederherzustellen.  
  
 In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareCtrl` für alle nicht-Edit-Steuerelemente für die sie Austauschen von Daten über DDX oder Validieren von Daten über DDV sind.  
  
 Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl  
 Das Framework ruft diese Memberfunktion um den angegebenen Edit-Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorzubereiten.  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDC`  
 Die ID des Bearbeitungssteuerelements für DDX oder DDV vorbereitet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HWND` des Bearbeitungssteuerelements DDX oder DDV vorbereitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [PrepareCtrl](#preparectrl) stattdessen für alle nicht-Edit-Steuerelemente.  
  
 Vorbereitung umfasst zwei Schritte. Erstens `PrepareEditCtrl` speichert des Steuerelements `HWND` in die `CDataExchange` Klasse. Das Framework verwendet dieses Handle, um den Fokus auf das Steuerelement zuvor mit Fokus im Fall eines Fehlers DDX oder DDV wiederherzustellen. Zweitens `PrepareEditCtrl` setzt ein Flag in der `CDataExchange` Klasse an, dass das Steuerelement, dessen Daten ausgetauscht werden oder ein Bearbeitungssteuerelement überprüft werden.  
  
 In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareEditCtrl` für alle Steuerelemente bearbeiten, für die sie Austauschen von Daten über DDX oder Validieren von Daten über DDV sind.  
  
 Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl  
 Das Framework ruft diese Memberfunktion, um das angegebene OLE-Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorzubereiten.  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDC`  
 Die ID des OLE-Steuerelements für DDX oder DDV vorbereitet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Website des OLE-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [PrepareEditCtrl](#prepareeditctrl) stattdessen für Bearbeitungssteuerelemente oder [PrepareCtrl](#preparectrl) für alle anderen nicht-OLE-Steuerelemente.  
  
 In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareOleCtrl` für alle OLE-Steuerelemente für die sie Austauschen von Daten über DDX oder Validieren von Daten über DDV sind.  
  
 Weitere Informationen über Ihre eigenen DDX- und DDV-Routinen schreiben, finden Sie unter [technischen Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel VIEWEX](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Ddx_managedcontrol](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

