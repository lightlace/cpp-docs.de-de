---
title: Standarddialog-Datenaustausch Routinen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 15bd88000a7a035ed416b7e1c0640488039079ab
ms.lasthandoff: 02/24/2017

---
# <a name="standard-dialog-data-exchange-routines"></a>Standard-Dialogdatenaustauschroutinen
Dieses Thema enthält die standardmäßigen Dialogdatenaustausch (DDX) Dialogfelddaten für allgemeine MFC-Dialogfeld-Steuerelemente verwendet.  
  
> [!NOTE]
>  Die standardmäßige dialogdatenaustauschroutinen werden in den Header-Datei afxdd_.h definiert. Allerdings sollten Applications afxwin.h enthalten.  
  
### <a name="ddx-functions"></a>DDX-Funktionen  
  
|||  
|-|-|  
|[DDX_CBIndex](#ddx_cbindex)|Initialisiert oder ruft den Index der aktuellen Auswahl ein Kombinationsfeld-Steuerelements ab.|  
|[DDX_CBString](#ddx_cbstring)|Initialisiert oder ruft den aktuellen Inhalt des Felds bearbeiten, der ein Kombinationsfeld-Steuerelement ab.|  
|[DDX_CBStringExact](#ddx_cbstringexact)|Initialisiert oder ruft den aktuellen Inhalt des Felds bearbeiten, der ein Kombinationsfeld-Steuerelement ab.|  
|[DDX_Check](#ddx_check)|Initialisiert oder ruft den aktuellen Zustand des Kontrollkästchen-Steuerelements.|  
|[DDX_Control](#ddx_control)|Unterklassen ein bestimmtes Steuerelement in einem Dialogfeld.|  
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Initialisiert oder ruft Datum und/oder eine Uhrzeit Daten von einer Datums- / Zeitauswahl-Steuerelement ab.|  
|[DDX_IPAddress](#ddx_ipaddress)|Initialisiert oder ruft den aktuellen Wert des Steuerelements für eine IP-Adressen.|  
|[DDX_LBIndex](#ddx_lbindex)|Initialisiert oder ruft den Index der aktuellen Auswahl von einem Listenfeld-Steuerelement ab.|  
|[DDX_LBString](#ddx_lbstring)|Initialisiert oder ruft die aktuelle Auswahl in einem Listenfeld-Steuerelement ab.|  
|[DDX_LBStringExact](#ddx_lbstringexact)|Initialisiert oder ruft die aktuelle Auswahl in einem Listenfeld-Steuerelement ab.|  
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Initialisiert oder ruft den aktuellen Wert des Monatskalender-Steuerelements.|  
|[DDX_Radio](#ddx_radio)|Initialisiert oder ruft ab, der 0-basierten Index des das Optionsfeld-Steuerelement, das derzeit in einer Optionsfeld-Steuerelement aktiviert ist.|  
|[DDX_Scroll](#ddx_scroll)|Initialisiert oder ruft die aktuelle Position des Ziehpunkts einen Bildlauf des Steuerelements ab.|  
|[DDX_Slider](#ddx_slider)|Initialisiert oder ruft ab der aktuellen Position des Ziehpunkts ein Schieberegler-Steuerelement.|  
|[DDX_Text](#ddx_text)|Initialisiert oder ruft den aktuellen Wert eines Steuerelements bearbeiten.|  
  
##  <a name="a-nameddxcbindexa--ddxcbindex"></a><a name="ddx_cbindex"></a>DDX_CBIndex  
 Die `DDX_CBIndex` Funktion verwaltet die Übertragung von `int` Daten zwischen einem Kombinationsfeld-Steuerelement in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `int` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID der zugeordneten Eigenschaft für das Kombinationsfeld-Steuerelement.  
  
 *Index*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_CBIndex` aufgerufen wird, *Index* auf den Index der aktuellen Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Index* auf 0 festgelegt ist.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxcbstringa--ddxcbstring"></a><a name="ddx_cbstring"></a>DDX_CBString  
 Die `DDX_CBString` Funktion verwaltet die Übertragung von `CString` Daten zwischen Bearbeitungssteuerelements ein Kombinationsfeld-Steuerelements in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `CString` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_CBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID der zugeordneten Eigenschaft für das Kombinationsfeld-Steuerelement.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_CBString` aufgerufen wird, *Wert* auf die aktuelle Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Kombinationsfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht auf 255 Zeichen beschränkt.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxcbstringexacta--ddxcbstringexact"></a><a name="ddx_cbstringexact"></a>DDX_CBStringExact  
 Die `DDX_CBStringExact` Funktion verwaltet die Übertragung von `CString` Daten zwischen Bearbeitungssteuerelements ein Kombinationsfeld-Steuerelements in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `CString` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID der zugeordneten Eigenschaft für das Kombinationsfeld-Steuerelement.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_CBStringExact` aufgerufen wird, *Wert* auf die aktuelle Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Kombinationsfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht auf 255 Zeichen beschränkt.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxchecka--ddxcheck"></a><a name="ddx_check"></a>DDX_Check  
 Die `DDX_Check` Funktion verwaltet die Übertragung von `int` Daten zwischen einer Kontrollkästchen-Steuerelement in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `int` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_Check(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Kontrollkästchen-Steuerelements, das die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Check` aufgerufen wird, *Wert* mit dem aktuellen Status des Kontrollkästchen-Steuerelements festgelegt ist. Eine Liste der möglichen Statuswerte, finden Sie unter [BM_GETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775986) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxcontrola--ddxcontrol"></a><a name="ddx_control"></a>DDX_Control  
 Die `DDX_Control` Funktion Unterklassen von angegebene Steuerelement `nIDC`des im Dialogfeld, in der Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_Control(
    CDataExchange* pDX,  
    int nIDC,  
    CWnd& rControl);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt.  
  
 `nIDC`  
 Die Ressourcen-ID des Steuerelements, das als Unterklasse definiert werden.  
  
 *rControl*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), Formularansicht oder Control-Objekt im Zusammenhang mit dem angegebenen Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die `pDX` wird bereitgestellt, die vom Framework bei der `DoDataExchange` -Funktion aufgerufen wird. Aus diesem Grund `DDX_Control` sollte nur aufgerufen werden, in der Überschreibung der `DoDataExchange`.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxdatetimectrla--ddxdatetimectrl"></a><a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl  
 Die `DDX_DateTimeCtrl` -Funktion verwaltet die Datenübertragung Datum und/oder eine Uhrzeit zwischen einer Datums- und Zeitauswahl ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) ein Dialogfeld oder Formular-Objekt und dann entweder eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Datenmember des Objekts anzeigen Dialogfeld oder Formular.  
  
```  
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen dieses Objekt löschen.  
  
 `nIDC`  
 Die Ressourcen-ID, der die Datums- / Zeitauswahl-Steuerelement die Membervariable zugeordnet werden soll.  
  
 *value*  
 In den ersten beiden Versionen, einen Verweis auf eine `CTime` oder `COleDateTime` Membervariable, (Dialogfeld), Formularansicht oder Control-Objekt mit dem Daten ausgetauscht werden. In der dritten Version, die einen Verweis auf eine `CString` Daten Mitgliedsobjekt Steuerelement anzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_DateTimeCtrl` aufgerufen wird, *Wert* festgelegt ist, auf den aktuellen Zustand des Datums und / Zeitauswahl-Steuerelement oder das Steuerelement wird auf festgelegt *Wert*, abhängig von der Richtung des Exchange.  
  
 In der dritten Version oben `DDX_DateTimeCtrl` verwaltet die Übertragung von `CString` Daten zwischen einem Datum /-Steuerelement und ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Datenmember des Objekts des Steuerelement-Ansicht. Die Zeichenfolge wird mithilfe von Regeln für das aktuelle Gebietsschema für die Formatierung von Datums- und Uhrzeitangaben formatiert.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxipaddressa--ddxipaddress"></a><a name="ddx_ipaddress"></a>DDX_IPAddress  
 Die `DDX_IPAddress` -Funktion verwaltet die Übertragung von Daten zwischen einer IP-Adresse und einen Datenmember des Steuerelementobjekts anzeigen.  
  
```  
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Steuerelements IP-Adresse der Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf die `DWORD` mit dem Wert&4;-Feld des Steuerelements für IP-Adressen. Die Felder ausgefüllt oder lauten.  
  
|Feld|Der Wert des Felds mit Bits|  
|-----------|-------------------------------------|  
|3|0 bis 7|  
|2|8 bis 15|  
|1|16 bis 23|  
|0|24 bis 31|  
  
 Verwenden Sie die Win32 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378) der Wert zu lesen, oder verwenden Sie [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380) zum Füllen des Werts. Diese Nachrichten werden gemäß der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_IPAddress` aufgerufen wird, *Wert* wird entweder aus dem Steuerelement IP-Adresse gelesen oder *Wert* bezieht sich auf das Steuerelement, je nach Richtung des Austauschs.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxlbindexa--ddxlbindex"></a><a name="ddx_lbindex"></a>DDX_LBIndex  
 Die `DDX_LBIndex` Funktion verwaltet die Übertragung von `int` Daten zwischen einem Listenfeld-Steuerelement in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `int` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Listenfeld-Steuerelements die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *Index*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_LBIndex` aufgerufen wird, *Index* auf den Index der aktuellen Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Index* wird auf-1 gesetzt.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxlbstringa--ddxlbstring"></a><a name="ddx_lbstring"></a>DDX_LBString  
 Die `DDX_LBString` Funktion verwaltet die Übertragung von `CString` Daten zwischen einem Listenfeld-Steuerelement in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `CString` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_LBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Listenfeld-Steuerelements die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_LBString` wird aufgerufen, um Daten an ein Listenfeld-Steuerelement, das erste Element im Steuerelement, deren Anfang übereinstimmt *Wert* ausgewählt ist. (Verwenden Sie entsprechend das gesamte Element, sondern nur ein Präfix, [DDX_LBStringExact](#ddx_lbstringexact).) Wenn keine Übereinstimmungen vorhanden sind, werden keine Elemente ausgewählt. Die Übereinstimmung wird Groß-und Kleinschreibung.  
  
 Wenn `DDX_LBString` wird aufgerufen, um das Übertragen von Daten aus einem Listenfeld-Steuerelement, *Wert* auf aktuelle Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Listenfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht auf 255 Zeichen beschränkt.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxlbstringexacta--ddxlbstringexact"></a><a name="ddx_lbstringexact"></a>DDX_LBStringExact  
 Die `DDX_CBStringExact` Funktion verwaltet die Übertragung von `CString` Daten zwischen der Edit-Steuerelement ein Listenfeld-Steuerelement in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `CString` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Listenfeld-Steuerelements die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_LBStringExact` wird aufgerufen, um das Übertragen von Daten in einem Listenfeld-Steuerelement, das erste Element im Steuerelement, das entspricht *Wert* ausgewählt ist. (Verwenden Sie entsprechend das gesamte Element, sondern nur ein Präfix, [DDX_LBString](#ddx_lbstring).) Wenn keine Übereinstimmungen vorhanden sind, werden keine Elemente ausgewählt. Die Übereinstimmung wird Groß-und Kleinschreibung.  
  
 Wenn `DDX_CBStringExact` wird aufgerufen, um das Übertragen von Daten aus einem Listenfeld-Steuerelement, *Wert* auf aktuelle Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Listenfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht auf 255 Zeichen beschränkt.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxmonthcalctrla--ddxmonthcalctrl"></a><a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl  
 Die `DDX_MonthCalCtrl` Funktion verwaltet die Übertragung von Daten zwischen einem Monatskalender-Steuerelement ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) in einem Dialogfeld, Formularansicht oder Control-Objekt und entweder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen dieses Objekt löschen.  
  
 `nIDC`  
 Die Ressourcen-ID, der im Monatskalender-Steuerelement zugeordnet ist die Membervariable.  
  
 *value*  
 Ein Verweis auf eine `CTime` oder `COleDateTime` Membervariable des Dialogfelds, Formularansicht oder Control-Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement verwaltet einen Date-Wert. Der Time-Felder in das Objekt sind auf den Zeitpunkt der Erstellung des Steuerelementfensters entsprechend festgelegt oder Zeitspanne festgelegt wurde, in das Steuerelement mit einem Aufruf von `CMonthCalCtrl::SetCurSel`.  
  
 Wenn `DDX_MonthCalCtrl` aufgerufen wird, *Wert* mit dem aktuellen Status des Monatskalender-Steuerelements festgelegt ist.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxradioa--ddxradio"></a><a name="ddx_radio"></a>DDX_Radio  
 Die `DDX_Radio` Funktion verwaltet die Übertragung von `int` Daten zwischen einer Optionsfeld-Steuerelement-Gruppe in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `int` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt. Der Wert von der `int` -Datenmember wird bestimmt anhand welches Schaltfläche in der Gruppe ausgewählt wird.  
  
```  
void AFXAPI DDX_Radio(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID, der das erste Optionsfeld-Steuerelement in der Gruppe.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Radio` aufgerufen wird, *Wert* auf den aktuellen Status der Gruppe das Optionsfeld festgelegt ist. Der Wert wird festgelegt, wie ein 0-basierten Index des das Optionsfeld-Steuerelement, das derzeit aktiviert ist, oder -1, wenn keine Optionsfeld-Steuerelemente werden überprüft.  
  
 Z. B. im Fall, der das erste Optionsfeld in der Gruppe ist aktiviert (der Schaltfläche mit WS_GROUP-Stil) den Wert von der `int` Member ist 0 und so weiter.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxscrolla--ddxscroll"></a><a name="ddx_scroll"></a>DDX_Scroll  
 Die `DDX_Scroll` Funktion verwaltet die Übertragung von `int` Daten zwischen einem Bildlaufleisten-Steuerelements in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `int` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Bildlaufleisten-Steuerelements die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf eine Membervariable des Dialogfelds, Formularansichts- oder Steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Scroll` aufgerufen wird, *Wert* an der aktuellen Position des Ziehpunkts für das Steuerelement festgelegt ist. Weitere Informationen zu der aktuellen Position des Ziehpunkts für das Steuerelement zugeordneten Werte, finden Sie unter [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxslidera--ddxslider"></a><a name="ddx_slider"></a>DDX_Slider  
 Die `DDX_Slider` Funktion verwaltet die Übertragung von `int` Daten zwischen ein Schieberegler-Steuerelement in einem Dialogfeld oder Formular anzeigen und ein `int` -Datenmember des Objekts anzeigen Dialogfeld oder Formular.  
  
```  
void AFXAPI DDX_Slider(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Schieberegler-Steuerelements.  
  
 *value*  
 Ein Verweis auf den Wert ausgetauscht werden sollen. Dieser Parameter enthält, oder legt die aktuelle Position des Schieberegler-Steuerelements fest.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Slider` aufgerufen wird, *Wert* festgelegt ist, an der aktuellen Position des Ziehpunkts für das Steuerelement, oder den Wert die Position, abhängig von der Richtung des Exchange empfängt.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="a-nameddxtexta--ddxtext"></a><a name="ddx_text"></a>DDX_Text  
 Die `DDX_Text` Funktion verwaltet die Übertragung von `int`, **UINT**, **lang**, `DWORD`, `CString`, **Float**, oder **doppelte** zwischen ein Edit-Steuerelement in einem Dialogfeld Formularansicht oder Ansicht steuern und eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
```  
void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID des ein Edit-Steuerelement im Dialogfeld, in der Formularansicht oder Control View-Objekt.  
  
 *value*  
 Ein Verweis auf einen Datenmember in das Dialogfeld, Formularansicht oder Control-Objekt. Der Datentyp des *Wert* hängt von der überladenen Versionen der `DDX_Text` Sie verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  

## <a name="see-also"></a>Siehe auch  
 [Standardroutinen Validierung für Dialogfelddaten](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

