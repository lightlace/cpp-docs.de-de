---
title: Dispatchzuordnungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5af6a8644514b18af3397fb22d54d42f649eed09
ms.sourcegitcommit: 05075fce8a0ed7fddb99f50f3931db966a91450d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271317"
---
# <a name="dispatch-maps"></a>Dispatchzuordnungen
OLE-Automatisierung bietet Möglichkeiten zum Aufrufen von Methoden und Eigenschaften für Anwendungen Zugriff auf. Der Mechanismus, durch die Microsoft Foundation Class-Bibliothek für die Verteilung dieser Anforderungen angegeben ist, die "Dispatchzuordnung" die internen und externen Namen des Objektfunktionen und Eigenschaften sowie die Datentypen, die von den Eigenschaften selbst und ausweist Funktionsargumente.  
  
### <a name="dispatch-maps"></a>Dispatchzuordnungen  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Deklariert, dass eine Dispatchzuordnung verwendet wird, um einer Klasse Methoden und Eigenschaften (muss in der Klassendeklaration verwendet werden) verfügbar zu machen.|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Startet die Definition eine Dispatchzuordnung.|  
|[END_DISPATCH_MAP](#end_dispatch_map)|Beendet die Definition eine Dispatchzuordnung.|  
|[DISP_FUNCTION](#disp_function)|In eine Dispatchzuordnung verwendet, um eine OLE-Automatisierung-Funktion zu definieren.|  
|[DISP_PROPERTY](#disp_property)|Definiert eine Eigenschaft der OLE-Automatisierung.|  
|[DISP_PROPERTY_EX](#disp_property_ex)|Definiert ein OLE-Automatisierungseigenschaft und benennt die Get- und Set-Funktionen.|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Definiert ein OLE-Automatisierungseigenschaft, mit der Benachrichtigung.|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Definiert eine Eigenschaft der OLE-Automatisierung, die Namen und Parameter die Get- und Set-Funktionen akzeptiert.|  
|[DISP_DEFVALUE](#disp_defvalue)|Stellt einer vorhandenen Eigenschaft den Standardwert eines Objekts an.|  
  
##  <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP  
 Wenn eine `CCmdTarget`-abgeleiteten Klasse in Ihrem Programm unterstützt OLE-Automatisierung, dass die Klasse eine Dispatchzuordnung, um seine Methoden und Eigenschaften verfügbar zu machen bereitgestellt werden muss.  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_DISPATCH_MAP` Makro am Ende der Klassendeklaration. Klicken Sie auf die. CPP-Datei, die das Element definiert Funktionen für die Klasse, verwenden Sie die `BEGIN_DISPATCH_MAP` Makro. Fügen Sie Makroeinträge für jede Ihrer Klasse Methoden und Eigenschaften verfügbar gemachte des ( `DISP_FUNCTION`, `DISP_PROPERTY`usw.). Verwenden Sie abschließend die `END_DISPATCH_MAP` Makro.  
  
> [!NOTE]
>  Wenn Sie keine Mitglieder nach dem deklarieren `DECLARE_DISPATCH_MAP`, müssen Sie einen neuen Zugriffstyp angeben ( **öffentlichen**, `private`, oder `protected`) für sie.  
  
 Die Anwendungs-Assistent und der Code-Assistenten helfen Automatisierungsklassen Erstellung und Verwaltung von Dispatchzuordnungen. Weitere Informationen zu Dispatchzuordnungen, finden Sie unter [Automatisierungsserver](../../mfc/automation-servers.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

##  <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP  
 Deklariert die Definition der Dispatchzuordnung.  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt den Namen der Klasse, die diese Dispatchzuordnung besitzt.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse der `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp), die die Memberfunktionen für die Klasse definiert, die Dispatchzuordnung, mit der `BEGIN_DISPATCH_MAP` -Makro, fügen Sie die Makroeinträge für alle Dispatch-Funktionen und Eigenschaften, und schließen Sie die Dispatchzuordnung, mit der `END_DISPATCH_MAP` Makro.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

##  <a name="end_dispatch_map"></a>  END_DISPATCH_MAP  
 Beendet die Definition der Dispatchzuordnung.  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Hinweise  
 Es muss verwendet werden, zusammen mit `BEGIN_DISPATCH_MAP`.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  

##  <a name="disp_function"></a>  DISP_FUNCTION  
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
 Ein Wert, der Rückgabetyp der Funktion.  
  
 `vtsParams`  
 Eine durch Leerzeichen getrennte Liste ein oder mehrere Konstanten, die die Parameterliste der Funktion angeben.  
  
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
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Die `vtsParams` Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der **VTS_** Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Ein auf ein Objekt angewendeter 
  
 [!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 Gibt eine Liste, die eine kurze ganze Zahl, gefolgt von einem Zeiger auf eine kurze ganze Zahl enthält.  
  
 Die **VTS_** Konstanten und ihre Bedeutungen lauten wie folgt:  
  
|Symbol|Parametertyp|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**Float**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY** oder **CY\***|  
|**VTS_DATE**|**DATE**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const-Variante\\ \***  oder **VARIANT &**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**kurze\\\***|  
|**VTS_PI4**|**lange\\\***|  
|**VTS_PR4**|**"Float"\\\***|  
|**VTS_PR8**|**Double\\\***|  
|**VTS_PCY**|**CY\\\***|  
|**VTS_PDATE**|**DATUM\\\***|  
|**VTS_PBSTR**|**BSTR\\\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\\\***|  
|**VTS_PSCODE**|**SCODE\\\***|  
|**VTS_PBOOL**|**BOOL\\\***|  
|**VTS_PVARIANT**|**VARIANT\\\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\\\***|  
|**VTS_NONE**|Kein Parameter|  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property"></a>  DISP_PROPERTY  
 Definiert ein OLE-Automatisierungseigenschaft in eine Dispatchzuordnung.  
  
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
 Ein Wert, der den Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Die `vtPropType` Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus den `VARENUM` Enumeration:  
  
|Symbol|**Eigenschaftentyp**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Wenn es sich bei ein externer Client ändert die Eigenschaft den Wert der Membervariable, die gemäß `memberName` ändert; es erfolgt keine Benachrichtigung über die Änderung.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property_ex"></a>  DISP_PROPERTY_EX  
 Ein OLE-Automatisierungseigenschaft und den Namen definiert der Funktionen abgerufen, und legen Sie den Wert der Eigenschaft in eine Dispatchzuordnung.  
  
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
 Name der Elementfunktion, die zum Abrufen der Eigenschaft verwendet.  
  
 `memberSet`  
 Name der Elementfunktion verwendet, um die Eigenschaft festzulegen.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Die `memberGet` und `memberSet` Funktionen haben Signaturen, die bestimmt, indem die `vtPropType` Argument. Die `memberGet` -Funktion akzeptiert keine Argumente und gibt einen Wert, der den vom angegebenen Typ `vtPropType`. Die `memberSet` Funktion akzeptiert ein Argument des Typs vom angegebenen `vtPropType` und nichts zurückgibt.  
  
 Die `vtPropType` Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus den `VARENUM` Enumeration. Eine Liste der folgenden Werte sind, finden Sie unter den Hinweisen für die `vtRetVal` im Parameters [DISP_FUNCTION](#disp_function). Beachten Sie, dass `VT_EMPTY`, aufgelistet in der `DISP_FUNCTION` "Hinweise", ist nicht als Eigenschaft-Datentyp zulässig.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY  
 Definiert ein OLE-Automatisierungseigenschaft, mit der Benachrichtigung in eine Dispatchzuordnung.  
  
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
 Name der Benachrichtigungsfunktion für die `szExternalName`.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu Eigenschaften, die mit definierten `DISP_PROPERTY`, eine Eigenschaft mit definierten `DISP_PROPERTY_NOTIFY` wird automatisch die angegebene Funktion aufrufen, `pfnAfterSet` Wenn die Eigenschaft geändert wird.  
  
 Die `vtPropType` Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus den `VARENUM` Enumeration:  
  
|Symbol|**Eigenschaftentyp**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM  
 Definiert eine Eigenschaft, die mit separaten zugegriffen **abrufen** und `Set` Memberfunktionen.  
  
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
 Name der Elementfunktion, die zum Abrufen der Eigenschaft verwendet.  
  
 `pfnSet`  
 Name der Elementfunktion verwendet, um die Eigenschaft festzulegen.  
  
 `vtPropType`  
 Ein Wert, der den Typ der Eigenschaft.  
  
 `vtsParams`  
 Eine Zeichenfolge mit Leerzeichen getrennten **VTS_** variant Parametertypen, eine für jeden Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den `DISP_PROPERTY_EX` Makro dieses Makro können Sie eine Parameterliste für die Eigenschaft angeben. Dies ist hilfreich bei der Implementierung von Eigenschaften, die indiziert oder parametrisiert werden.  
  
### <a name="example"></a>Beispiel  
 Betrachten Sie die folgende Deklaration von Get, und legen Sie Member Funktionen, mit die Benutzer einer bestimmten Zeile und Spalte anfordern, wenn die Eigenschaft zugreifen können:  
  
 [!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 Diese entsprechen dem folgenden `DISP_PROPERTY_PARAM` Makro in die Dispatchzuordnung Steuerelement:  
  
 [!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 Ein weiteres Beispiel sollten Sie die folgenden Get, und legen Sie Member Funktionen aus:  
  
 [!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 Diese entsprechen dem folgenden `DISP_PROPERTY_PARAM` Makro in die Dispatchzuordnung Steuerelement:  
  
 [!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

##  <a name="disp_defvalue"></a>  DISP_DEFVALUE  
 Stellt einer vorhandenen Eigenschaft den Standardwert eines Objekts an.  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse.  
  
 `pszName`  
 Externer Name der Eigenschaft, die den "Wert" des Objekts darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Standardwert, kann die Programmierung Ihr Automatisierungsobjekts, das für Visual Basic-Anwendungen einfacher machen.  
  
 Der "Default Value" des Objekts ist die Eigenschaft, die abgerufen oder festgelegt werden, wenn ein Verweis auf ein Objekt eine Eigenschaft oder der Member-Funktion nicht angegeben wird.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
