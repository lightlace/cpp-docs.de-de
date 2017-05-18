---
title: Dispatchzuordnungen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps. macros
- dispatch maps
- dispatch map macros
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
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
ms.openlocfilehash: 48e5d1fe207089733caa5ed9e8ca30c2de21f95f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="dispatch-maps"></a>Dispatchzuordnungen
OLE-Automatisierung bietet Methoden zum Aufrufen von Methoden und Eigenschaften über die Anwendung zugreifen. Der Mechanismus, der vom Microsoft Foundation Class-Bibliothek zum Weiterleiten dieser Anforderungen ist die "Dispatchzuordnung" die internen und externen Namen des Objekt-Funktionen und Eigenschaften als auch die Datentypen der Eigenschaften angezeigt und der Funktionsargumente ausweist.  
  
### <a name="dispatch-maps"></a>Dispatchzuordnungen  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Deklariert, dass eine Dispatchzuordnung verwendet wird, um einer Klasse Methoden und Eigenschaften (muss in der Klassendeklaration verwendet werden) verfügbar zu machen.|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Startet die Definition eine Dispatchzuordnung.|  
|[END_DISPATCH_MAP](#end_dispatch_map)|Beendet die Definition eine Dispatchzuordnung.|  
|[DISP_FUNCTION](#disp_function)|In eine Dispatchzuordnung verwendet, um ein OLE-Automatisierung-Funktion zu definieren.|  
|[DISP_PROPERTY](#disp_property)|Definiert eine Eigenschaft der OLE-Automatisierung.|  
|[DISP_PROPERTY_EX](#disp_property_ex)|Definiert eine Eigenschaft der OLE-Automatisierung und benennt die Get- und Set-Funktionen.|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Definiert eine OLE-Automatisierungseigenschaft Benachrichtigung.|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Definiert eine Eigenschaft der OLE-Automatisierung, die Namen und Parameter die Get- und Set-Funktionen akzeptiert.|  
|[DISP_DEFVALUE](#disp_defvalue)|Wird einer vorhandenen Eigenschaft den Standardwert eines Objekts.|  
  
##  <a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP  
 Wenn eine `CCmdTarget`-abgeleiteten Klasse in Ihrem Programm unterstützt die OLE-Automatisierung, Klasse eine Dispatchzuordnung, um seine Methoden und Eigenschaften verfügbar machen muss.  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_DISPATCH_MAP` Makro am Ende der Klassendeklaration. Klicken Sie auf die. CPP-Datei, die das Element definiert für die Klasse funktioniert, verwenden Sie die `BEGIN_DISPATCH_MAP` Makro. Fügen Sie Makroeinträge für jede Ihrer Klasse verfügbar gemacht Methoden und Eigenschaften werden die ( `DISP_FUNCTION`, `DISP_PROPERTY`usw.). Verwenden Sie schließlich die `END_DISPATCH_MAP` Makro.  
  
> [!NOTE]
>  Wenn Sie keine Mitglieder nach dem deklarieren `DECLARE_DISPATCH_MAP`, geben Sie einen neuen Zugriffstyp ( **öffentlichen**, `private`, oder `protected`) für sie.  
  
 Die Anwendungsassistenten und Code-Assistenten helfen, Automatisierungsklassen Erstellung und Verwaltung von Dispatchzuordnungen. Weitere Informationen zu Dispatchzuordnungen, finden Sie unter [Automatisierungsserver](../../mfc/automation-servers.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation&#10;](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

##  <a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP  
 Deklariert die Definition der Dispatchzuordnung.  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt den Namen der Klasse, die diese Dispatchzuordnung besitzt.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse des `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp)-Datei, die Memberfunktionen für die Klasse definiert, die Dispatchzuordnung, mit der `BEGIN_DISPATCH_MAP` Makro Makroeinträge für jede der Dispatch-Funktionen und Eigenschaften hinzufügen, und führen Sie die Dispatchzuordnung, mit der `END_DISPATCH_MAP` Makro.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

##  <a name="end_dispatch_map"></a>END_DISPATCH_MAP  
 Beendet die Definition der Dispatchzuordnung.  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Hinweise  
 Es muss verwendet werden, in Verbindung mit `BEGIN_DISPATCH_MAP`.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

##  <a name="disp_function"></a>DISP_FUNCTION  
 Definiert eine Funktion der OLE-Automatisierung in eine Dispatchzuordnung.  
  
```   
DISP_FUNCTION(
  theClass, 
  pszName, 
  pfnMember, 
  vtRetVal, 
  vtsParams)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Funktion.  
  
 `pfnMember`  
 Der Name der Elementfunktion.  
  
 `vtRetVal`  
 Ein Wert, der den Rückgabetyp der Funktion angeben.  
  
 `vtsParams`  
 Eine durch Leerzeichen getrennte Liste von ein oder mehrere Konstanten, die Parameterliste für die Funktion angeben.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtRetVal` Argument ist vom Typ **VARTYPE**. Die folgenden möglichen Werte für dieses Argument stammen aus den `VARENUM` Enumeration:  
  
|Symbol|Rückgabetyp|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATUM**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (keine Kommas) gibt die Parameterliste der Funktion an. Beispiel: 
  
 [!code-cpp[NVC_MFCAutomation&14;](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 Gibt eine Liste, die eine kurze ganze Zahl, gefolgt von einem Zeiger und eine kurze ganze Zahl enthält.  
  
 Die **VTS_** Konstanten und ihre Bedeutungen lauten wie folgt:  
  
|Symbol|Parametertyp|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**Float**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY** oder **CY\***|  
|**VTS_DATE**|**DATUM**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const-Variante\* ** oder **VARIANT &**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**kurze\***|  
|**VTS_PI4**|**lange\***|  
|**VTS_PR4**|**float\***|  
|**VTS_PR8**|**Double\***|  
|**VTS_PCY**|**CY\***|  
|**VTS_PDATE**|**DATUM\***|  
|**VTS_PBSTR**|**BSTR\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\***|  
|**VTS_PSCODE**|**SCODE\***|  
|**VTS_PBOOL**|**BOOL\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\***|  
|**VTS_NONE**|Ohne Parameter|  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property"></a>DISP_PROPERTY  
 Definiert eine OLE-Automatisierungseigenschaft in eine Dispatchzuordnung.  
  
```   
DISP_PROPERTY(
  theClass, 
  pszName, 
  memberName, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `memberName`  
 Name der Membervariable, in der die Eigenschaft gespeichert ist.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtPropType` Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus den `VARENUM` Enumeration:  
  
|Symbol|**Eigenschaftentyp**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATUM**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Wenn ein externer Client ändert die Eigenschaft den Wert der angegebenen Membervariable `memberName` geändert wird, erfolgt keine Benachrichtigung über die Änderung.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property_ex"></a>DISP_PROPERTY_EX  
 Definiert ein OLE-Automatisierungseigenschaft und Name die Funktionen zum Abrufen und Festlegen des Eigenschaftswerts in eine Dispatchzuordnung.  
  
```   
DISP_PROPERTY_EX(
  theClass, 
  pszName, 
  memberGet, 
  memberSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft.  
  
 `memberGet`  
 Name der Elementfunktion zum Abrufen der Eigenschaft verwendet.  
  
 `memberSet`  
 Name der Elementfunktion zum Festlegen der Eigenschaft.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die `memberGet` und `memberSet` Funktionen verfügen über Signaturen, die anhand der `vtPropType` Argument. Die `memberGet` -Funktion akzeptiert keine Argumente und gibt einen Wert des angegebenen Typs `vtPropType`. Die `memberSet` Funktion ein Argument des Typs vom angegebenen `vtPropType` und gibt nichts zurück.  
  
 Die `vtPropType` Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus den `VARENUM` Enumeration. Eine Liste dieser Werte finden Sie unter den Hinweisen zu den `vtRetVal` -Parameter in [DISP_FUNCTION](#disp_function). Beachten Sie, dass `VT_EMPTY`, aufgelistet in den `DISP_FUNCTION` Hinweise, ist nicht als Eigenschaftendatentyp zulässig.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY  
 Definiert eine OLE-Automatisierungseigenschaft Benachrichtigung in eine Dispatchzuordnung.  
  
```   
DISP_PROPERTY_NOTIFY(
  theClass, 
  szExternalName, 
  memberName, 
  pfnAfterSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `szExternalName`  
 Externer Name der Eigenschaft.  
  
 `memberName`  
 Name der Membervariable, in der die Eigenschaft gespeichert ist.  
  
 `pfnAfterSet`  
 Name der Benachrichtigungsfunktion für `szExternalName`.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft angibt.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu Eigenschaften, die mit definierten `DISP_PROPERTY`, eine Eigenschaft mit `DISP_PROPERTY_NOTIFY` ruft automatisch die angegebene Funktion `pfnAfterSet` Wenn die Eigenschaft geändert wird.  
  
 Die `vtPropType` Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus den `VARENUM` Enumeration:  
  
|Symbol|**Eigenschaftentyp**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATUM**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property_param"></a>DISP_PROPERTY_PARAM  
 Definiert eine Eigenschaft mit separaten zugegriffen **abrufen** und `Set` Memberfunktionen.  
  
```   
DISP_PROPERTY_PARAM(
  theClass, 
  pszExternalName, 
  pfnGet, 
  pfnSet, 
  vtPropType,
  vtsParams)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 *pszExternalName*  
 Externer Name der Eigenschaft.  
  
 `pfnGet`  
 Name der Elementfunktion zum Abrufen der Eigenschaft verwendet.  
  
 `pfnSet`  
 Name der Elementfunktion zum Festlegen der Eigenschaft.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft angibt.  
  
 `vtsParams`  
 Eine Zeichenfolge mit Leerzeichen getrennte **VTS_** variant Parametertypen, einen für jeden Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den `DISP_PROPERTY_EX` Makro dieses Makros können Sie eine Parameterliste für die Eigenschaft an. Dies ist nützlich zum Implementieren von Eigenschaften, die indiziert oder parametrisiert werden.  
  
### <a name="example"></a>Beispiel  
 Betrachten Sie die folgende Deklaration der Get und -Member Funktionen, mit denen den Benutzer beim Zugriff auf die Eigenschaft einer bestimmten Zeile und Spalte anfordern:  
  
 [!code-cpp[NVC_MFCActiveXControl&#9;](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 Diese entsprechen den folgenden `DISP_PROPERTY_PARAM` Makro Dispatchzuordnung des Steuerelements:  
  
 [!code-cpp[NVC_MFCActiveXControl&#10;](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 Als weiteres Beispiel sollten Sie die folgenden Get und set Member-Funktionen:  
  
 [!code-cpp[NVC_MFCActiveXControl&#11;](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 Diese entsprechen den folgenden `DISP_PROPERTY_PARAM` Makro Dispatchzuordnung des Steuerelements:  
  
 [!code-cpp[NVC_MFCActiveXControl&#12;](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_defvalue"></a>DISP_DEFVALUE  
 Wird einer vorhandenen Eigenschaft den Standardwert eines Objekts.  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft, die die "Value" des Objekts darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Standardwert kann stellen das Automatisierungsobjekt für Visual Basic-Anwendung einfacher zu programmieren.  
  
 Der "Standardwert" des Objekts ist die Eigenschaft, die abgerufen oder festgelegt werden, wenn ein Verweis auf ein Objekt eine Eigenschaft oder Member-Funktion nicht angegeben wird.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

