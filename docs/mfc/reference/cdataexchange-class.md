---
title: CDataExchange-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- DDX/DDV, Technical Note 26
- DDX/DDV, CDataExchange class
- DDX (dialog data exchange), direction of exchange
- DDX (dialog data exchange), between dialog and CDialog
- DDX (dialog data exchange), custom DDX routines
- DDV (dialog data validation)
- m_bSaveAndValidate
- CDataExchange class
- exchanging data between dialogs and CDialogs
- DDV (dialog data validation), custom DDV routines
- DDX/DDV
- DDX (dialog data exchange)
- validating data, dialog box data entry
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8f35e87d562a894411401755ccd4fdd54e43b58a
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdataexchange-class"></a>CDataExchange-Klasse
Unterstützt die Routinen für den Dialogdatenaustausch (Dialog Data Exchange, DDX) und die Dialogfelddatenvalidierung (Dialog Data Validation, DDV), die von den Microsoft Foundation-Klassen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|Erstellt ein `CDataExchange`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|Wird aufgerufen, wenn die Validierung fehlschlägt. Setzt den Fokus auf das vorherige Steuerelement zurück und löst eine Ausnahme aus.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|Das angegebene Steuerelement vorbereitet für den Datenaustausch oder Überprüfung. Verwenden Sie für Nonedit-Steuerelemente.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Das angegebene Edit-Steuerelement vorbereitet für den Datenaustausch oder Überprüfung.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Das angegebene OLE-Steuerelement vorbereitet für den Datenaustausch oder Überprüfung. Verwenden Sie für Nonedit-Steuerelemente.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Das Flag für die Richtung des DDX- und DDV.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Die im Dialogfeld bzw. Fenster, in denen der Datenaustausch, erfolgt.|  
  
## <a name="remarks"></a>Hinweise  
 `CDataExchange`eine Basisklasse keinen.  
  
 Verwenden Sie diese Klasse, wenn Sie Daten Exchange Routinen für benutzerdefinierte Datentypen oder Steuerelemente, Schreiben Sie eigene datenvalidierungsroutine schreiben. Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfelder](../../mfc/dialog-boxes.md).  
  
 Ein `CDataExchange` Objekt enthält die Kontextinformationen für DDX- und DDV auszuführende platzieren erforderlich sind. Das Flag `m_bSaveAndValidate` ist **FALSE** Wenn DDX füllen die Anfangswerte des Dialogfeld-Steuerelemente von Datenmember verwendet wird. Das Flag `m_bSaveAndValidate` ist **TRUE** Wenn DDX verwendet wird, die aktuellen Werte der Dialogfeld-Steuerelemente in der Datenmember und wenn DDV verwendet wird, zum Überprüfen der Datenwerte festgelegt. Die DDV-Überprüfung fehlschlägt, wird der DDV-Prozedur ein Meldungsfeld zum Eingaben-Fehler angezeigt. Ruft die Prozedur DDV dann **fehl** um den Fokus auf das problematische Steuerelement zurückgesetzt und löst eine Ausnahme aus, um den Überprüfungsprozess zu beenden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDataExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cdataexchange"></a>CDataExchange::CDataExchange  
 Rufen Sie diese Memberfunktion zum Erstellen einer `CDataExchange` Objekt.  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>Parameter  
 *pDlgWnd*  
 Ein Zeiger auf das übergeordnete Fenster, das das Steuerelement enthält. Dies ist normalerweise ein [CDialog](../../mfc/reference/cdialog-class.md)-abgeleitetes Objekt.  
  
 `bSaveAndValidate`  
 Wenn **TRUE**, dieses Objekt überprüft Daten, und schreibt Daten über die Steuerelemente für die Elemente. Wenn **FALSE**, dieses Objekt wird Daten von Mitgliedern zu Steuerelementen wechseln.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CDataExchange` Objekt zum Speichern von zusätzlichen Informationen in der Exchange-Datenobjekt Übergabe an des Fensters selbst [Ddx_managedcontrol](../../mfc/reference/cwnd-class.md#dodataexchange) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#70;](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>CDataExchange::Fail  
 Das Framework ruft diese Member-Funktion, wenn ein Dialogfeld Daten-Überprüfung (DDV)-Vorgang fehlschlägt.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>Hinweise  
 **Fehler** stellt den Fokus und Auswahl an das Steuerelement, dessen Überprüfung fehlgeschlagen (wenn ein Steuerelement wiederherstellen) wieder her. **Ein Fehler auf** löst dann eine Ausnahme vom Typ [CUserException](../../mfc/reference/cuserexception-class.md) den Überprüfungsprozess zu beenden. Die Ausnahme bewirkt, dass ein Meldungsfeld, einer Beschreibung des Fehlers angezeigt werden. Wenn DDV-Validierung fehlgeschlagen ist, kann Benutzer Daten im betreffenden Steuerelement eingeben.  
  
 Beim Implementieren benutzerdefinierter DDV-Routinen können Aufrufen **fehl** aus ihren Routinen, die bei einem Überprüfungsfehler fehlschlägt.  
  
 Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate  
 Dieses Flag gibt die Richtung eines Dialogfeld Datenvorgangs Dialogdatenaustausch (DDX).  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Flag ist ungleich NULL Wenn die `CDataExchange` Objekt verwendet wird, um Daten aus dem Dialogfeld-Steuerelemente in Dialogklasse Datenmember verschieben, nachdem der Benutzer die Steuerelemente bearbeitet. Das Flag ist&0; (null), wenn das Objekt initialisiert Dialogfeld-Steuerelemente von Dialogfeldklasse Datenmember verwendet wird.  
  
 Das Flag ist auch beim Validieren von Dialogfelddaten (DDV) ungleich NULL ist.  
  
 Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd  
 Enthält einen Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) Objekt, für welches Dialogfeld Daten Dialogdatenaustausch (DDX) oder Überprüfung (DDV) erfolgt.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt stellt normalerweise eine [CDialog](../../mfc/reference/cdialog-class.md) Objekt. In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen können this-Zeiger, den Zugriff auf das Dialogfeld, das Steuerelemente enthält, auf der Sie ausgeführt werden.  
  
 Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="preparectrl"></a>CDataExchange::PrepareCtrl  
 Das Framework ruft diese Memberfunktion, um das angegebene Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorbereiten.  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDC`  
 Die ID des Steuerelements für DDX oder DDV vorbereitet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HWND` des Steuerelements für den DDX oder DDV vorbereitet.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie [PrepareEditCtrl](#prepareeditctrl) Bearbeitungssteuerelementen; verwenden Sie stattdessen diese Memberfunktion für alle anderen Steuerelemente.  
  
 Vorbereitung umfasst das Speichern des Steuerelements `HWND` in der `CDataExchange` Klasse. Das Framework verwendet dieses Handle, um den Fokus auf das zuvor fokussierte Steuerelement bei Auftreten eines Fehlers DDX oder DDV wiederherstellen.  
  
 In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareCtrl` für alle nicht-Edit-Steuerelemente für den Datenaustausch über DDX oder werden Daten über DDV überprüfen.  
  
 Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareeditctrl"></a>CDataExchange::PrepareEditCtrl  
 Das Framework ruft diese Memberfunktion zum angegebenen Bearbeitungssteuerelement für Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorbereiten.  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDC`  
 Die ID des Bearbeitungssteuerelements für DDX oder DDV vorbereitet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HWND` des Bearbeitungssteuerelements für DDX oder DDV vorbereitet.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [PrepareCtrl](#preparectrl) stattdessen für alle nicht-Edit-Steuerelemente.  
  
 Vorbereitung umfasst zwei Schritte. Erstens `PrepareEditCtrl` speichert das Steuerelement `HWND` in der `CDataExchange` Klasse. Das Framework verwendet dieses Handle, um den Fokus auf das zuvor fokussierte Steuerelement bei Auftreten eines Fehlers DDX oder DDV wiederherstellen. Zweitens `PrepareEditCtrl` setzt ein Flag in der `CDataExchange` Klasse an, dass das Steuerelement, dessen Daten ausgetauscht werden oder ein Bearbeitungssteuerelement überprüft werden.  
  
 In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareEditCtrl` für alle Steuerelemente bearbeiten, für die sie den Austausch von Daten über DDX oder Überprüfen von Daten über DDV.  
  
 Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareolectrl"></a>CDataExchange::PrepareOleCtrl  
 Das Framework ruft diese Memberfunktion, um das angegebene OLE-Steuerelement für den Dialogdatenaustausch (DDX) und Überprüfung (DDV) vorbereiten.  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDC`  
 Die ID des OLE-Steuerelements für DDX oder DDV vorbereitet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Website des OLE-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [PrepareEditCtrl](#prepareeditctrl) stattdessen für Edit-Steuerelemente oder [PrepareCtrl](#preparectrl) für alle anderen nicht-OLE-Steuerelemente.  
  
 In einer Implementierung von benutzerdefinierten DDX oder DDV-Routinen sollten Aufrufen `PrepareOleCtrl` für alle OLE-Steuerelemente für den Datenaustausch über DDX oder werden Daten über DDV überprüfen.  
  
 Weitere Informationen zum Schreiben eigene DDX- und DDV-Routinen, finden Sie unter [Technische Hinweis 26](../../mfc/tn026-ddx-and-ddv-routines.md). Eine Übersicht über DDX- und DDV, finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md) und [Dialogfeldthemen](../../mfc/dialog-boxes.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel Wahl](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Ddx_managedcontrol](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)


