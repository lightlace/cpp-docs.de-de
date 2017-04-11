---
title: Standarddialog-Datenaustausch Routinen | Microsoft Docs
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 86491a06a81f5b0ddf0c91c9c5f2b5f23261b49b
ms.lasthandoff: 04/04/2017

---
# <a name="standard-dialog-data-exchange-routines"></a>Standard-Dialogdatenaustauschroutinen
Dieses Thema enthält die standardmäßigen (Dialogdatenaustausch DDX) dialogdatenaustauschroutinen für allgemeine MFC-Dialogfeld-Steuerelemente verwendet.  
  
> [!NOTE]
>  Der standard dialogdatenaustauschroutinen werden in die Header-Datei afxdd_.h definiert. Allerdings sollten Anwendungen afxwin.h enthalten.  
  
### <a name="ddx-functions"></a>DDX-Funktionen  
  
|||  
|-|-|  
|[DDX_CBIndex](#ddx_cbindex)|Initialisiert oder ruft den Index der aktuellen Auswahl von einem Kombinationsfeld-Steuerelement ab.|  
|[DDX_CBString](#ddx_cbstring)|Initialisiert oder ruft den aktuellen Inhalt des Felds bearbeiten, der ein Kombinationsfeld-Steuerelement ab.|  
|[DDX_CBStringExact](#ddx_cbstringexact)|Initialisiert oder ruft den aktuellen Inhalt des Felds bearbeiten, der ein Kombinationsfeld-Steuerelement ab.|  
|[DDX_Check](#ddx_check)|Initialisiert oder ruft den aktuellen Zustand von Kontrollkästchen-Steuerelement.|  
|[DDX_Control](#ddx_control)|Unterklassen ein bestimmtes Steuerelement in einem Dialogfeld.|  
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Initialisiert oder ruft ab Datum und/oder eine Uhrzeit Daten eines Steuerelements für Datums- und Zeitauswahl.|  
|[DDX_IPAddress](#ddx_ipaddress)|Initialisiert oder ruft den aktuellen Wert einer IP-Adressensteuerelement ab.|  
|[DDX_LBIndex](#ddx_lbindex)|Initialisiert oder ruft den Index der aktuellen Auswahl von einem Listenfeld-Steuerelement ab.|  
|[DDX_LBString](#ddx_lbstring)|Initialisiert oder ruft die aktuelle Auswahl in einem Listenfeld-Steuerelement ab.|  
|[DDX_LBStringExact](#ddx_lbstringexact)|Initialisiert oder ruft die aktuelle Auswahl in einem Listenfeld-Steuerelement ab.|
|[DDX_ManagedControl](#ddx_managedcontrol)|Erstellt ein .NET Steuerelement übereinstimmenden Ressourcen-ID für das Steuerelement|  
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Initialisiert oder ruft den aktuellen Wert für ein Monatskalender-Steuerelement ab.|  
|[DDX_Radio](#ddx_radio)|Initialisiert oder ruft ab, der 0-basierte Index des das Optionsfeld-Steuerelement, das derzeit in einer Steuerelementgruppe Optionsfeld aktiviert ist.|  
|[DDX_Scroll](#ddx_scroll)|Initialisiert oder ruft die aktuelle Position des Ziehpunkts ein Bildlaufleisten-Steuerelement ab.|  
|[DDX_Slider](#ddx_slider)|Initialisiert oder ruft die aktuelle Position des Ziehpunkts ein Schieberegler-Steuerelement ab.|  
|[DDX_Text](#ddx_text)|Initialisiert oder ruft ab den aktuellen Wert eines Bearbeitungssteuerelements.|  
  
##  <a name="ddx_cbindex"></a>DDX_CBIndex  
 Die `DDX_CBIndex` -Funktion verwaltet die Übertragung von `int` Daten zwischen einem Kombinationsfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Die Ressourcen-ID der zugeordneten Steuerelementeigenschaft ein Kombinationsfeld-Steuerelement.  
  
 *Index*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_CBIndex` aufgerufen wird, *Index* auf den Index der aktuellen Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Index* auf 0 festgelegt ist.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_cbstring"></a>DDX_CBString  
 Die `DDX_CBString` -Funktion verwaltet die Übertragung von `CString` Daten zwischen den Edit-Steuerelement von einem Kombinationsfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Die Ressourcen-ID der zugeordneten Steuerelementeigenschaft ein Kombinationsfeld-Steuerelement.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_CBString` aufgerufen wird, *Wert* auf der aktuellen Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Kombinationsfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht maximal 255 Zeichen enthalten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_cbstringexact"></a>DDX_CBStringExact  
 Die `DDX_CBStringExact` -Funktion verwaltet die Übertragung von `CString` Daten zwischen den Edit-Steuerelement von einem Kombinationsfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Die Ressourcen-ID der zugeordneten Steuerelementeigenschaft ein Kombinationsfeld-Steuerelement.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_CBStringExact` aufgerufen wird, *Wert* auf der aktuellen Auswahl aus dem Kombinationsfeld festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Kombinationsfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht maximal 255 Zeichen enthalten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_check"></a>DDX_Check  
 Die `DDX_Check` -Funktion verwaltet die Übertragung von `int` Daten zwischen einem Kontrollkästchen-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Die Ressourcen-ID, der das Kontrollkästchensteuerelement die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Check` aufgerufen wird, *Wert* mit dem aktuellen Status des Kontrollkästchen-Steuerelements festgelegt ist. Eine Liste der möglichen Zustandswerte finden Sie unter [BM_GETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775986) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_control"></a>DDX_Control  
 Die `DDX_Control` Funktion Unterklassen von angegebene Steuerelement `nIDC`des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, die im Zusammenhang mit dem angegebenen Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die `pDX` -Objekt vom Framework bereitgestellt wird bei der `DoDataExchange` Funktion aufgerufen wird. Aus diesem Grund `DDX_Control` sollte nur aufgerufen werden, in der Außerkraftsetzung von `DoDataExchange`.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl  
 Die `DDX_DateTimeCtrl` -Funktion verwaltet die Datenübertragung Datum und/oder eine Uhrzeit zwischen die Datumsauswahl ein Datum und Uhrzeit ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) in ein Dialogfeld oder Formular Ansichtsobjekt und entweder eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Datenmember des Dialogfeld oder Formular View-Objekts.  
  
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
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen nicht das Objekt gelöscht werden.  
  
 `nIDC`  
 Die Ressourcen-ID, der das Datum und Uhrzeit Kontoauswahl-Steuerelement die Membervariable zugeordnet werden soll.  
  
 *value*  
 In den ersten beiden Versionen, die einen Verweis auf eine `CTime` oder `COleDateTime` Membervariable, (Dialogfeld), Formular- oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden. In der dritten Version, die einen Verweis auf eine `CString` Datenmember steuerungsansichtsobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_DateTimeCtrl` aufgerufen wird, *Wert* festgelegt ist, mit dem aktuellen Zustand der das Datum und Uhrzeit Kontoauswahl-Steuerelement oder das Steuerelement wird festgelegt, um *Wert*, abhängig von der Richtung des Austausches.  
  
 In der dritten Version, die oben genannten `DDX_DateTimeCtrl` verwaltet die Übertragung von `CString` Daten zwischen einem Datum Uhrzeit Steuerelement und ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Datenmember des Steuerelementobjekts anzeigen. Die Zeichenfolge wird mithilfe von Regeln für das aktuelle Gebietsschema für die Formatierung von Datums- und Uhrzeitangaben formatiert.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  

   

 
## <a name="ddx_managedcontrol"></a>DDX_ManagedControl
Erstellt ein .NET Steuerelement übereinstimmenden Ressourcen-ID für das Steuerelement  
   
### <a name="syntax"></a>Syntax  
  ```  
template <typename T>  
void DDX_ManagedControl(  
     CDataExchange* pDX,   
     int nIDC,   
     CWinFormsControl<T>& control );  
```
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange-Klasse](cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Steuerelements die Steuerelementeigenschaft zugeordnet werden soll.  
  
 `control`  
 Ein Verweis auf eine [CWinFormsControl Klasse](cwinformscontrol-class.md) Objekt.  
   
### <a name="remarks"></a>Hinweise  
 `DDX_ManagedControl`Aufrufe [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol) Erstellen eines Steuerelements mit der Ressource Steuerelement-ID übereinstimmt. Verwendung `DDX_ManagedControl` So erstellen Sie Steuerelemente aus der Ressourcen-IDs in [CDialog::](cdialog-class.md#oninitdialog). Für den Datenaustausch müssen Sie nicht die DDX-/DDV-Funktionen mit Windows Forms-Steuerelemente verwenden.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Führen Sie DDX-/DDV-Datenbindung mit Windows Forms](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
   
### <a name="see-also"></a>Siehe auch  
 [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)   
 [CDialog::](cdialog-class.md#oninitdialog)
 

  
##  <a name="ddx_ipaddress"></a>DDX_IPAddress  
 Die `DDX_IPAddress` -Funktion verwaltet die Übertragung von Daten zwischen einem Steuerelement für die IP-Adresse und einen Datenmember des Steuerelementobjekts anzeigen.  
  
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
 Ein Verweis auf die `DWORD` mit dem Wert 4-Feld des Steuerelements für IP-Adressen. Die Felder ausgefüllt oder wie folgt lesen.  
  
|Feld|Bits, die den Wert des Felds enthält.|  
|-----------|-------------------------------------|  
|3|0 bis 7|  
|2|8 bis 15|  
|1|16 bis 23|  
|0|24 bis 31|  
  
 Verwenden Sie die Win32 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378) , lesen den Wert ein, oder verwenden Sie [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380) um den Wert zu füllen. Diese Nachrichten werden gemäß der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_IPAddress` aufgerufen wird, *Wert* wird entweder aus der IP-Adressensteuerelement gelesen oder *Wert* an das Steuerelement, je nach Richtung des Austausches geschrieben wird.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_lbindex"></a>DDX_LBIndex  
 Die `DDX_LBIndex` -Funktion verwaltet die Übertragung von `int` Daten zwischen einem Listenfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_LBIndex` aufgerufen wird, *Index* auf den Index der aktuellen Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Index* auf-1 festgelegt ist.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_lbstring"></a>DDX_LBString  
 Die `DDX_LBString` -Funktion verwaltet die Übertragung von `CString` Daten zwischen einem Listenfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_LBString` wird aufgerufen, um ein Listenfeld-Steuerelement, das erste Element im Steuerelement Datenübertragung, deren Beginn übereinstimmt *Wert* ausgewählt ist. (Verwenden, um nur ein Präfix, anstatt das gesamte Element übereinstimmt, [DDX_LBStringExact](#ddx_lbstringexact).) Wenn keine Übereinstimmungen vorhanden sind, sind keine Elemente ausgewählt. Der Abgleich wird die Groß-/Kleinschreibung.  
  
 Wenn `DDX_LBString` zum Übertragen von Daten aus einem Listenfeld-Steuerelement, heißt *Wert* auf die aktuelle Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Listenfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht maximal 255 Zeichen enthalten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_lbstringexact"></a>DDX_LBStringExact  
 Die `DDX_CBStringExact` -Funktion verwaltet die Übertragung von `CString` Daten zwischen den Edit-Steuerelement ein Listenfeld-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `CString` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_LBStringExact` wird aufgerufen, um Daten an ein Listenfeld-Steuerelement, das erste Element im Steuerelement zu übertragen, die entspricht *Wert* ausgewählt ist. (Verwenden Sie entsprechend das gesamte Element, sondern nur ein Präfix, [DDX_LBString](#ddx_lbstring).) Wenn keine Übereinstimmungen vorhanden sind, sind keine Elemente ausgewählt. Der Abgleich wird die Groß-/Kleinschreibung.  
  
 Wenn `DDX_CBStringExact` zum Übertragen von Daten aus einem Listenfeld-Steuerelement, heißt *Wert* auf die aktuelle Auswahl des Listenfelds festgelegt ist. Wenn kein Element ausgewählt ist, *Wert* in eine Zeichenfolge der Länge Null festgelegt ist.  
  
> [!NOTE]
>  Wenn das Listenfeld ein Dropdown-Listenfeld ist, ist der Wert, der ausgetauscht maximal 255 Zeichen enthalten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl  
 Die `DDX_MonthCalCtrl` -Funktion verwaltet die Übertragung von Datumsdaten zwischen einem Monatskalender-Steuerelement ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) in ein Dialogfeld, Formularansicht oder steuerungsansichtsobjekts und entweder eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen nicht das Objekt gelöscht werden.  
  
 `nIDC`  
 Die Ressourcen-ID, der im Monatskalender-Steuerelement, die die Membervariable zugeordnet ist.  
  
 *value*  
 Ein Verweis auf eine `CTime` oder `COleDateTime` Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Das Steuerelement wird nur einen Datumswert verwaltet. Zeitfelder in das Objekt sind entsprechend dem Zeitpunkt der Erstellung des Steuerelementfensters oder ein Zeitspanne festgelegt wurde, in das Steuerelement mit einem Aufruf von `CMonthCalCtrl::SetCurSel`.  
  
 Wenn `DDX_MonthCalCtrl` aufgerufen wird, *Wert* festgelegt ist, auf den aktuellen Zustand der im Monatskalender-Steuerelement.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_radio"></a>DDX_Radio  
 Die `DDX_Radio` -Funktion verwaltet die Übertragung von `int` Daten zwischen einer Steuerelementgruppe Optionsfelder in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt. Der Wert, der die `int` Datenmember richtet sich entsprechend die Optionsfelder innerhalb der Gruppe ausgewählt ist.  
  
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
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Radio` aufgerufen wird, *Wert* auf den aktuellen Status der Gruppe "Steuerelement Radio" festgelegt ist. Der Wert wird festgelegt, wie ein 0-basierten Index des das Optionsfeld-Steuerelement, das derzeit aktiviert ist, oder-1 zurück, wenn keine Optionsfeld-Steuerelementen überprüft werden.  
  
 Beispielsweise im Fall, der das erste Optionsfeld in der Gruppe ist aktiviert (der Schaltfläche mit WS_GROUP-Stil) den Wert von der `int` Member ist 0 und so weiter.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_scroll"></a>DDX_Scroll  
 Die `DDX_Scroll` -Funktion verwaltet die Übertragung von `int` Daten zwischen einem Bildlaufleisten-Steuerelements in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Wenn `DDX_Scroll` aufgerufen wird, *Wert* auf der aktuellen Position des Ziehpunkts für das Steuerelement festgelegt ist. Weitere Informationen auf der aktuellen Position des Ziehpunkts für das Steuerelement zugeordneten Werte finden Sie unter [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_slider"></a>DDX_Slider  
 Die `DDX_Slider` -Funktion verwaltet die Übertragung von `int` Daten zwischen ein Schieberegler-Steuerelement in einem Dialogfeld Feld oder Formularansicht und eine `int` -Datenmember des Dialogfeld oder Formular View-Objekts.  
  
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
 Ein Verweis auf den Wert ausgetauscht werden sollen. Dieser Parameter enthält, oder legt die aktuelle Position das Schieberegler-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_Slider` aufgerufen wird, *Wert* festgelegt ist, an der aktuellen Position des Ziehpunkts für das Steuerelement, oder der Wert empfängt die Position, je nach Richtung des Austausches.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  
  
##  <a name="ddx_text"></a>DDX_Text  
 Die `DDX_Text` -Funktion verwaltet die Übertragung von `int`, **"uint"**, **lange**, `DWORD`, `CString`, **"float"**, oder **doppelte** Daten zwischen einem Edit-Steuerelement in einem Dialogfeld Formularansicht oder Ansicht steuern und eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
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
 Die ID eines Bearbeitungssteuerelements im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekts.  
  
 *value*  
 Ein Verweis auf einen Datenmember im Dialogfeld, in der Formularansicht oder steuerungsansichtsobjekts. Der Datentyp des *Wert* hängt von dem der überladenen Versionen der `DDX_Text` Sie verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdd_.h  

## <a name="see-also"></a>Siehe auch  
 [Standardroutinen zur Validierung Dialogfelddaten](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

