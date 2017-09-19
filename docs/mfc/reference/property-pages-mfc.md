---
title: Eigenschaftenseiten (MFC) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages, global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 50888697fe01d3a84d9aa4c6f5f92926e4681535
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="property-pages-mfc"></a>Eigenschaftenseiten (MFC)
Eigenschaftenseiten anzeigen die aktuellen Werte der Eigenschaften für bestimmte OLE-Steuerelements in einer anpassbaren, grafische Schnittstelle zum Anzeigen und Bearbeiten von Daten Zuordnungsmechanismus basierend auf den Dialogdatenaustausch (DDX) unterstützen.  
  
 Dieser Mechanismus Zuordnung ordnet Seitensteuerelemente-Eigenschaft die einzelnen Eigenschaften des OLE-Steuerelements. Der Wert der Steuerelementeigenschaft zeigt den Status oder den Inhalt eines Steuerelements die Eigenschaft. Die Zuordnung zwischen Eigenschaften und Steuerelemente der Seite Eigenschaft wird angegeben, indem **DDP_** -Funktionsaufrufe in der Eigenschaftenseite `DoDataExchange` Member-Funktion. Im folgenden werden eine Liste der **DDP_** Funktionen, die exchange-Daten mithilfe der Eigenschaftenseite des Steuerelements eingegeben wird:  
  
### <a name="property-page-data-transfer"></a>Eigenschaft Seite Datenübertragung  
  
|||  
|-|-|  
|[DDP_CBIndex](#ddp_cbindex)|Verknüpft die ausgewählte Zeichenfolge Index in einem Kombinationsfeld mit einer Steuerelementeigenschaft.|  
|[DDP_CBString](#ddp_cbstring)|Verknüpft die ausgewählte Zeichenfolge in einem Kombinationsfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge kann mit denselben Buchstaben wie der Wert der Eigenschaft beginnen jedoch nicht vollständig Übereinstimmung.|  
|[DDP_CBStringExact](#ddp_cbstringexact)|Verknüpft die ausgewählte Zeichenfolge in einem Kombinationsfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge und der Zeichenfolgenwert der Eigenschaft müssen exakt übereinstimmen.|  
|[DDP_Check](#ddp_check)|Verknüpft ein Kontrollkästchen, das Steuerelement auf der Seite mit einer Steuerelementeigenschaft.|  
|[DDP_LBIndex](#ddp_lbindex)|Verknüpft die ausgewählte Zeichenfolge Index in einem Listenfeld mit einer Steuerelementeigenschaft.|  
|[DDP_LBString](#ddp_lbstring)|Verknüpft die ausgewählte Zeichenfolge in einem Listenfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge kann mit denselben Buchstaben wie der Wert der Eigenschaft beginnen, aber es muss nicht vollständig damit übereinstimmen.|  
|[DDP_LBStringExact](#ddp_lbstringexact)|Verknüpft die ausgewählte Zeichenfolge in einem Listenfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge und der Zeichenfolgenwert der Eigenschaft müssen exakt übereinstimmen.|  
|[DDP_PostProcessing](#ddp_postprocessing)|Beendet die Übertragung von Eigenschaftswerten über das Steuerelement.|  
|[DDP_Radio](#ddp_radio)|Links eine Gruppe von Optionsfeldern des Steuerelements auf der Seite mit einer Steuerelementeigenschaft.|  
|[DDP_Text](#ddp_text)|Verknüpft ein Steuerelement des Steuerelements auf der Seite mit einer Steuerelementeigenschaft. Diese Funktion behandelt verschiedene Arten von Eigenschaften, z. B. **doppelte**, **kurze**, `BSTR`, und **lang**.|  
  
 Weitere Informationen zu den `DoDataExchange` -Funktion oder auf den Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
 Im folgenden finden eine Liste der Makros, die zum Erstellen und Verwalten von Eigenschaftenseiten für ein OLE-Steuerelement:  
  
### <a name="property-pages"></a>Eigenschaftenseiten  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Beginnt die Liste der Eigenschaftenseiten-IDs.|  
|[END_PROPPAGEIDS](#end_proppageids)|Die Liste der Eigenschaftenseiten-IDs wird beendet.|  
|[PROPPAGEID](#proppageid)|Deklariert eine Eigenschaftenseite der Control-Klasse.|  
  
##  <a name="ddp_cbindex"></a>DDP_CBIndex  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert der Integer-Eigenschaft mit dem Index der aktuellen Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kombinationsfeld-Feld mit dem angegebenen Steuerelementeigenschaft zugeordnete Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname des Steuerelementeigenschaft ausgetauscht werden, mit der angegebenen Kombinationsfeld-Steuerelement `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_CBIndex` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_cbstring"></a>DDP_CBString  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft mit der aktuellen Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kombinationsfeld-Feld mit dem angegebenen Steuerelementeigenschaft zugeordnete Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftenname, der Steuerelementeigenschaft, der mit der angegebenen Kombinationsfeld Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_CBString` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_cbstringexact"></a>DDP_CBStringExact  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft zu synchronisieren, die die aktuelle Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite genau übereinstimmt.  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kombinationsfeld-Feld mit dem angegebenen Steuerelementeigenschaft zugeordnete Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftenname, der Steuerelementeigenschaft, der mit der angegebenen Kombinationsfeld Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_CBStringExact` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_check"></a>DDP_Check  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert der Eigenschaft mit dem zugeordneten Eigenschaft Seite das Kontrollkästchen-Steuerelement zu synchronisieren.  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kontrollkästchen-Steuerelements mit dem angegebenen Steuerelementeigenschaft zugeordnete `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftenname, der Steuerelementeigenschaft mit dem Kontrollkästchen-Steuerelement angegeben durch ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_Check` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_lbindex"></a>DDP_LBIndex  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert der Integer-Eigenschaft mit dem Index der aktuellen Auswahl in einem Listenfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID der Liste im Feld mit dem angegebenen Steuerelementeigenschaft zugeordnete Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Die Eigenschaftennname der Steuerelementeigenschaft, der mit der angegebenen Liste Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_LBIndex` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_lbstring"></a>DDP_LBString  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft mit der aktuellen Auswahl in einem Listenfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID der Liste im Feld mit dem angegebenen Steuerelementeigenschaft zugeordnete Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Die Eigenschaftennname der Steuerelementeigenschaft, der mit der angegebenen Liste Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_LBString` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_lbstringexact"></a>DDP_LBStringExact  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Zeichenfolgeneigenschaft zu synchronisieren, die die aktuelle Auswahl in einem Listenfeld auf der Eigenschaftenseite genau übereinstimmt.  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID der Liste im Feld mit dem angegebenen Steuerelementeigenschaft zugeordnete Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Die Eigenschaftennname der Steuerelementeigenschaft, der mit der angegebenen Liste Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_LBStringExact` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_postprocessing"></a>DDP_PostProcessing  
 Mit dieser Funktion wird die Eigenschaftenseite `DoDataExchange` -Funktion verwendet, um die Übertragung von Eigenschaftswerten auf der Eigenschaftenseite an das Steuerelement Fertig stellen, wenn Eigenschaftswerte gespeichert werden.  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, nachdem alle Datenaustauschfunktionen abgeschlossen wurden. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAxCtl&#15;](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_radio"></a>DDP_Radio  
 Rufen Sie diese Funktion in Ihrem Steuerelements `DoPropExchange` Funktion, um den Wert der Eigenschaft mit der zugehörigen Eigenschaft Seite Optionsfeld-Steuerelement zu synchronisieren.  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Senders Schaltfläche zugeordnete Steuerelementeigenschaft, die vom angegebenen Steuerelement `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftenname, der Steuerelementeigenschaft, der mit das RadioButton-Steuerelement durch angegebene ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_Radio` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_text"></a>DDP_Text  
 Rufen Sie diese Funktion in Ihrem Steuerelements `DoDataExchange` Funktion, um den Wert der Eigenschaft mit dem Steuerelement zugeordnete Eigenschaft zu synchronisieren.  
  
```   
void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    BYTE & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    UINT & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    long & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    DWORD & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    float & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    double & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    CString & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf ein `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Steuerelements mit der angegebenen Eigenschaft des Steuerelements verknüpften `pszPropName`.  
  
 `member`  
 Membervariable, die durch angegebene Eigenschaft Seitensteuerelement zugeordnete `id` und der angegebenen Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Die Eigenschaftennname der Steuerelementeigenschaft mit dem angegebenen Steuerelement ausgetauscht werden sollen `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aufgerufen werden, bevor Sie die entsprechenden `DDX_Text` -Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="begin_proppageids"></a>BEGIN_PROPPAGEIDS  
 Beginn der Definition des Steuerelements Liste der Eigenschaftenseiten-IDs.  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name von der Control-Klasse, die für die Eigenschaft Seiten angegeben werden.  
  
 *count*  
 Die Anzahl der Eigenschaftenseiten, die von der Control-Klasse verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp)-Datei, die Memberfunktionen für die Klasse definiert, die Eigenschaftenliste für die Seite mit der `BEGIN_PROPPAGEIDS` -Makro, dann fügen Sie die Makroeinträge für jede Eigenschaft, und schließen Sie die Eigenschaftenliste für die Seite mit der `END_PROPPAGEIDS` Makro.  
  
 Weitere Informationen zu den Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="end_proppageids"></a>END_PROPPAGEIDS  
 Beendet die Definition der Eigenschaft ID Seitenliste.  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name der Control-Klasse, die die Eigenschaftenseite besitzt.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="proppageid"></a>PROPPAGEID  
 Eine Eigenschaftenseite für die Verwendung hinzugefügt durch das OLE-Steuerelement.  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Die eindeutige Klassen-ID einer Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Alle `PROPPAGEID` Makros platziert werden müssen, zwischen dem `BEGIN_PROPPAGEIDS` und `END_PROPPAGEIDS` Makros in der Implementierungsdatei des Steuerelements.  

### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

