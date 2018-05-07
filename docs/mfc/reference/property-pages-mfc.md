---
title: Eigenschaftenseiten (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0895cd22870b3a4a266e9be12f0000fae7f7101a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="property-pages-mfc"></a>Eigenschaftenseiten (MFC)
Eigenschaftenseiten werden die aktuellen Werte von bestimmten Eigenschaften der OLE-Steuerelements in eine anpassbare, grafische Benutzeroberfläche zum Anzeigen und bearbeiten, durch die Unterstützung einer datenzuordnung Authentifizierungsmechanismus auf Grundlage der Dialogdatenaustausch (DDX) angezeigt.  
  
 Dieser Mechanismus datenzuordnung ordnet Seitensteuerelemente Eigenschaft auf die einzelnen Eigenschaften des OLE-Steuerelements an. Der Wert der Steuerelementeigenschaft spiegelt wider, den Status oder den Inhalt des Steuerelements Seite Eigenschaft. Die Zuordnung zwischen Eigenschaften und Seitensteuerelemente Eigenschaft wird angegeben, indem **DDP_** -Funktionsaufrufe in der Eigenschaftenseite `DoDataExchange` Memberfunktion. Im folgenden werden eine Liste der **DDP_** Funktionen, die exchange-Daten mithilfe der Eigenschaftenseite des Steuerelements eingegeben:  
  
### <a name="property-page-data-transfer"></a>Eigenschaft Seitendaten Übertragung  
  
|||  
|-|-|  
|[DDP_CBIndex](#ddp_cbindex)|Verknüpft die ausgewählte Zeichenfolge Index in einem Kombinationsfeld mit einer Steuerelementeigenschaft.|  
|[DDP_CBString](#ddp_cbstring)|Verknüpft die ausgewählte Zeichenfolge in ein Kombinationsfeld, mit der Eigenschaft eines Steuerelements an. Die ausgewählte Zeichenfolge mit den gleichen Buchstaben als Wert der Eigenschaft beginnen kann, aber nicht vollständig Übereinstimmung.|  
|[DDP_CBStringExact](#ddp_cbstringexact)|Verknüpft die ausgewählte Zeichenfolge in ein Kombinationsfeld, mit der Eigenschaft eines Steuerelements an. Der markierten Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|  
|[DDP_Check](#ddp_check)|Verknüpft ein Kontrollkästchen auf der Eigenschaftenseite des Steuerelements mit der Eigenschaft eines Steuerelements an.|  
|[DDP_LBIndex](#ddp_lbindex)|Verknüpft die ausgewählte Zeichenfolge Index in einem Listenfeld mit der Eigenschaft eines Steuerelements an.|  
|[DDP_LBString](#ddp_lbstring)|Verknüpft die ausgewählte Zeichenfolge in einem Listenfeld mit der Eigenschaft eines Steuerelements an. Die ausgewählte Zeichenfolge dieselben Buchstaben als Wert der Eigenschaft kann beginnen, darf jedoch muss nicht vollständig damit übereinstimmen.|  
|[DDP_LBStringExact](#ddp_lbstringexact)|Verknüpft die ausgewählte Zeichenfolge in einem Listenfeld mit der Eigenschaft eines Steuerelements an. Der markierten Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|  
|[DDP_PostProcessing](#ddp_postprocessing)|Beendet die Übertragung von Eigenschaftswerten über das Steuerelement an.|  
|[DDP_Radio](#ddp_radio)|Links eine Gruppe von Optionsfeldern des Steuerelements auf der Seite mit der Eigenschaft des Steuerelements.|  
|[DDP_Text](#ddp_text)|Verknüpft ein Steuerelement des Steuerelements auf der Seite mit der Eigenschaft eines Steuerelements an. Diese Funktion behandelt verschiedene Typen von Eigenschaften, z. B. **doppelte**, **kurze**, `BSTR`, und **lang**.|  
  
 Weitere Informationen zu den `DoDataExchange` -Funktion oder auf den Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
 Im folgenden finden eine Liste von Makros, die zum Erstellen und Verwalten von Eigenschaftenseiten für OLE-Steuerelements verwendet:  
  
### <a name="property-pages"></a>Eigenschaftenseiten  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Beginnt die Liste der Eigenschaftenseiten-IDs an.|  
|[END_PROPPAGEIDS](#end_proppageids)|Die Liste der Eigenschaftenseite IDs wird beendet.|  
|[PROPPAGEID](#proppageid)|Deklariert eine Eigenschaftenseite von der Control-Klasse.|  
  
##  <a name="ddp_cbindex"></a>  DDP_CBIndex  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Eigenschaft für die ganze Zahl mit dem Index der aktuellen Auswahl im Kombinationsfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kombinationsfeld Feld zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit dem Kombinationsfeld-Steuerelement, das gemäß ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_CBIndex` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_cbstring"></a>  DDP_CBString  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Eigenschaft für die Zeichenfolge mit der aktuellen Auswahl im Kombinationsfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kombinationsfeld Feld zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit der angegebenen Zeichenfolge im Feld Kombinationsfeld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_CBString` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert, der eine Zeichenfolgeneigenschaft zu synchronisieren, die die aktuelle Auswahl in einem Kombinationsfeld auf der Eigenschaftenseite genau übereinstimmt.  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Kombinationsfeld Feld zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit der angegebenen Zeichenfolge im Feld Kombinationsfeld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_CBStringExact` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_check"></a>  DDP_Check  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert der Eigenschaft mit der zugehörigen Eigenschaft Seite Kontrollkästchen-Steuerelement zu synchronisieren.  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID, der das Kontrollkästchensteuerelement zugeordneten Steuerelementeigenschaft, die vom angegebenen `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit dem angegeben wird, indem Sie das Kontrollkästchen-Steuerelement ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_Check` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_lbindex"></a>  DDP_LBIndex  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Eigenschaft für die ganze Zahl mit dem Index für die aktuelle Auswahl in einem Listenfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID der Liste Feld zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit der angegebenen Liste Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_LBIndex` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_lbstring"></a>  DDP_LBString  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert einer Eigenschaft für die Zeichenfolge mit der aktuellen Auswahl in einem Listenfeld auf der Eigenschaftenseite zu synchronisieren.  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID der Liste Feld zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit der angegebenen Liste Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_LBString` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` Funktion, um den Wert, der eine Zeichenfolgeneigenschaft zu synchronisieren, die die aktuelle Auswahl in einem Listenfeld auf der Eigenschaftenseite genau übereinstimmt.  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID der Liste Feld zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit der angegebenen Liste Feld ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_LBStringExact` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing  
 Mit dieser Funktion wird auf der Eigenschaftenseite `DoDataExchange` -Funktion verwendet, um die Übertragung von Eigenschaftswerte auf der Eigenschaftenseite an das Steuerelement Fertig stellen, wenn Eigenschaftswerte gespeichert werden.  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, nachdem alle Datenaustauschfunktionen abgeschlossen wurden. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_radio"></a>  DDP_Radio  
 Mit dieser Funktion wird in des Steuerelements `DoPropExchange` Funktion, um den Wert der Eigenschaft mit der zugehörigen Eigenschaft Seite Optionsfeld-Steuerelement zu synchronisieren.  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des Optionsfelds Schaltfläche zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit das Optionsfeld-Steuerelement durch angegebenen ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_Radio` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="ddp_text"></a>  DDP_Text  
 Mit dieser Funktion wird in des Steuerelements `DoDataExchange` Funktion, um den Wert der Eigenschaft mit dem Steuerelement zugeordnete Eigenschaft zu synchronisieren.  
  
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
 Zeiger auf eine `CDataExchange` Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `id`  
 Die Ressourcen-ID des zugeordneten Steuerelementeigenschaft, die vom angegebenen Steuerelements `pszPropName`.  
  
 `member`  
 Die Membervariable, die die Eigenschaft Seitensteuerelement gemäß zugeordnet `id` und durch die angegebene Eigenschaft `pszPropName`.  
  
 `pszPropName`  
 Der Eigenschaftsname der Steuerelementeigenschaft, der mit dem Steuerelement gemäß ausgetauscht werden `id`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte aufgerufen werden, bevor das entsprechende `DDX_Text` Funktionsaufruf.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS  
 Die Definition der Steuerelementliste der Eigenschaftenseite IDs beginnt.  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse, die für die Eigenschaft Seiten angegeben werden.  
  
 *count*  
 Die Anzahl der Eigenschaftenseiten, die von der Control-Klasse verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp), die die Memberfunktionen für die Klasse definiert, die Seite-Eigenschaftenliste mit der `BEGIN_PROPPAGEIDS` -Makro, dann fügen Sie für jeden der Eigenschaftenseiten Makroeinträge hinzu, und schließen Sie die Seite-Eigenschaftenliste mit der `END_PROPPAGEIDS` Makro.  
  
 Weitere Informationen zu Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="end_proppageids"></a>  END_PROPPAGEIDS  
 Beendet die Definition der Eigenschaft Seite ID enthalten.  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse, die die Eigenschaftsseite "besitzt.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="proppageid"></a>  PROPPAGEID  
 Fügt eine Eigenschaftenseite für die Verwendung von OLE-Steuerelements an.  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Die eindeutige Klassen-ID einer Eigenschaftenseite.  
  
### <a name="remarks"></a>Hinweise  
 Alle `PROPPAGEID` Makros müssen platziert werden, zwischen den `BEGIN_PROPPAGEIDS` und `END_PROPPAGEIDS` Makros in der Implementierungsdatei des Steuerelements.  

### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
