---
title: Dispatchzuordnungen
ms.date: 06/20/2018
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 5ebedaa02a03bcc7802110977b96659dae45f174
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585080"
---
# <a name="dispatch-maps"></a>Dispatchzuordnungen

OLE-Automatisierung bietet Möglichkeiten zum Aufrufen von Methoden und Eigenschaften in Anwendungen zugreifen. Der Mechanismus, der vom Microsoft Foundation Class-Bibliothek für die Verteilung dieser Anforderungen ist die "Dispatchzuordnung" die internen und externen Namen des Objekt-Funktionen und Eigenschaften als auch die Datentypen, die von den Eigenschaften selbst und ausweist Argumente der Funktion.

|Dispatch-Map-Makro|Beschreibung|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Deklariert, dass eine Dispatchzuordnung verwendet wird, um Methoden und Eigenschaften (muss in der Klassendeklaration verwendet werden) einer Klasse verfügbar zu machen.|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Startet die Definition eine Dispatchzuordnung.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Beendet die Definition eine Dispatchzuordnung.|
|[DISP_FUNCTION](#disp_function)|In einer Dispatchzuordnung verwendet, um eine OLE-Automatisierung-Funktion zu definieren.|
|[DISP_PROPERTY](#disp_property)|Definiert eine Eigenschaft der OLE-Automatisierung.|
|[DISP_PROPERTY_EX](#disp_property_ex)|Definiert eine Eigenschaft der OLE-Automatisierung und benennt die Get- und Set-Funktionen.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Definiert ein OLE-Automatisierungseigenschaft mit der Benachrichtigung.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Definiert eine Eigenschaft der OLE-Automatisierung, die Namen und Parameter die Get- und Set-Funktionen akzeptiert.|
|[DISP_DEFVALUE](#disp_defvalue)|Wird einer vorhandenen Eigenschaft den Standardwert eines Objekts an.|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

Wenn eine `CCmdTarget`-abgeleiteten Klasse in Ihrem Programm unterstützt die OLE-Automatisierung, dass die Klasse eine Dispatchzuordnung, um seine Methoden und Eigenschaften verfügbar zu machen bereitstellen muss.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Hinweise

Verwenden Sie das DECLARE_DISPATCH_MAP-Makro, am Ende der Klassendeklaration. Klicken Sie auf der. CPP-Datei, die die Member-Funktionen für die Klasse definiert. verwenden Sie das BEGIN_DISPATCH_MAP-Makro. Klicken Sie dann enthalten Sie Makroeinträge, für alle Ihre Klasse verfügbar gemachten Methoden und Eigenschaften (DISP_FUNCTION DISP_PROPERTY und So weiter). Verwenden Sie abschließend die END_DISPATCH_MAP-Makro.

> [!NOTE]
> Wenn Sie Mitglieder nach DECLARE_DISPATCH_MAP deklarieren, müssen Sie einen neuen Zugriffstyp angeben ( **öffentliche**, **private**, oder **geschützt**) für sie.

Die Anwendungs-Assistenten und Code-Assistenten helfen bei der Erstellung des Automation-Klassen und Verwaltung von Dispatchzuordnungen. Weitere Informationen zu Dispatchzuordnungen, finden Sie unter [Automatisierungsserver](../../mfc/automation-servers.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP

Deklariert die Definition Ihrer Dispatchzuordnung.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Gibt den Namen der Klasse, die diese Dispatchzuordnung besitzt.

*Basisklasse*<br/>
Gibt den Namen der Basisklasse des *TheClass*.

### <a name="remarks"></a>Hinweise

Starten Sie in der Implementierungsdatei (.cpp), die die Member-Funktionen für die Klasse definiert die Dispatchzuordnung, mit dem BEGIN_DISPATCH_MAP-Makro, fügen Sie die Makroeinträge für jede Ihrer Dispatch-Funktionen und Eigenschaften und abgeschlossen die Dispatchzuordnung, mit der END_DISPATCH_ MAP-Makro.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

Beendet die Definition Ihrer Dispatchzuordnung.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Hinweise

Es muss in Verbindung mit BEGIN_DISPATCH_MAP verwendet werden.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

Definiert eine Funktion der OLE-Automatisierung in eine Dispatchzuordnung.

```cpp
DISP_FUNCTION(
  theClass,
  pszName,
  pfnMember,
  vtRetVal,
  vtsParams)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Funktion.

*pfnMember*<br/>
Der Name der Elementfunktion.

*vtRetVal*<br/>
Ein Wert, der Rückgabetyp der Funktion angibt.

*vtsParams*<br/>
Eine durch Leerzeichen getrennte Liste von einer oder mehrerer Konstanten, die Parameterliste der Funktion angeben.

### <a name="remarks"></a>Hinweise

Die *VtRetVal* Argument ist vom Typ VARTYPE. Die folgenden möglichen Werte für dieses Argument stammen aus der `VARENUM` Enumeration:

|Symbol|Rückgabetyp|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

Die *VtsParams* Argument ist eine durch Leerzeichen getrennte Liste von Werten aus der `VTS_*` Konstanten. Eine oder mehrere dieser Werte getrennt durch Leerzeichen (nicht Kommas) gibt die Parameterliste der Funktion an. Ein auf ein Objekt angewendeter

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

Gibt eine Liste, enthält eine kurze ganze Zahl, gefolgt von einem Zeiger in einen short Integer.

Die `VTS_` Konstanten und ihre Bedeutungen lauten wie folgt:

|Symbol|Parametertyp|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` oder `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPDISPATCH|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` oder `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__kurze\*__|
|VTS_PI4|__long\*__|
|VTS_PR4|__float\*__|
|VTS_PR8|__Double-Wert\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|Ohne Parameter|

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="disp_property"></a>  DISP_PROPERTY

Definiert eine Eigenschaft der OLE-Automatisierung in eine Dispatchzuordnung.

```cpp
DISP_PROPERTY(
  theClass,
  pszName,
  memberName,
  vtPropType)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Eigenschaft.

*MemberName*<br/>
Der Name der Membervariablen, die in der die Eigenschaft gespeichert wird.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

### <a name="remarks"></a>Hinweise

Die *VtPropType* Argument ist vom Typ **VARTYPE**. Mögliche Werte für dieses Argument stammen aus der Enumeration VARENUM:

|Symbol|Eigenschaftentyp|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

Wenn ein externer Client ändert die Eigenschaft, die den Wert der Membervariable gemäß *MemberName* Änderungen; es erfolgt keine Benachrichtigung über die Änderung.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="disp_property_ex"></a>  DISP_PROPERTY_EX

Einen OLE-Automatisierungseigenschaft und den Namen definiert der Funktionen, die abgerufen, und legen Sie den Wert der Eigenschaft in eine Dispatchzuordnung.

```cpp
DISP_PROPERTY_EX(
  theClass,
  pszName,
  memberGet,
  memberSet,
  vtPropType)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Eigenschaft.

*memberGet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft abzurufen.

*"MemberSet"*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft festzulegen.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

### <a name="remarks"></a>Hinweise

Die *MemberGet* und *"MemberSet"* Funktionen haben Signaturen, die bestimmt, indem die *VtPropType* Argument. Die *MemberGet* Funktion akzeptiert keine Argumente und gibt einen Wert, der den vom angegebenen Typ *VtPropType*. Die *"MemberSet"* Funktion akzeptiert ein Argument des Typs vom angegebenen *VtPropType* und gibt nichts zurück.

Die *VtPropType* Argument ist vom Typ VARTYPE. Mögliche Werte für dieses Argument stammen aus der Enumeration VARENUM. Eine Liste der Werte, finden Sie unter den Hinweisen zu den *VtRetVal* Parameter im [DISP_FUNCTION](#disp_function). Beachten Sie, die VT_EMPTY, aufgeführt in den Hinweisen DISP_FUNCTION als Datentyp für eine Eigenschaft nicht zulässig ist.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

Definiert ein OLE-Automatisierungseigenschaft mit der Benachrichtigung in eine Dispatchzuordnung.

```cpp
DISP_PROPERTY_NOTIFY(
  theClass,
  szExternalName,
  memberName,
  pfnAfterSet,
  vtPropType)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*szExternalName*<br/>
Externer Name der Eigenschaft.

*MemberName*<br/>
Der Name der Membervariablen, die in der die Eigenschaft gespeichert wird.

*pfnAfterSet*<br/>
Name der Benachrichtigungsfunktion für *SzExternalName*.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu Eigenschaften, die mit DISP_PROPERTY definiert werden, ruft eine Eigenschaft mit DISP_PROPERTY_NOTIFY definiert automatisch die Funktion anhand des *PfnAfterSet* Wenn die Eigenschaft geändert wird.

Die *VtPropType* Argument ist vom Typ VARTYPE. Mögliche Werte für dieses Argument stammen aus der Enumeration VARENUM:

|Symbol|Eigenschaftentyp|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM

Definiert eine Eigenschaft zugegriffen wird, mit separaten `Get` und `Set` Memberfunktionen.

```cpp
DISP_PROPERTY_PARAM(
  theClass,
  pszExternalName,
  pfnGet,
  pfnSet,
  vtPropType,
  vtsParams)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszExternalName*<br/>
Externer Name der Eigenschaft.

*pfnGet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft abzurufen.

*pfnSet*<br/>
Der Name der Memberfunktion verwendet, um die Eigenschaft festzulegen.

*vtPropType*<br/>
Ein Wert, der den Typ der Eigenschaft angibt.

*vtsParams*<br/>
Eine Zeichenfolge mit durch Leerzeichen getrennte `VTS_*` variant Parametertypen, eine für jeden Parameter.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu den DISP_PROPERTY_EX-Makro ermöglicht Ihnen die Angabe eine Liste der Parameter für die Eigenschaft dieses Makro. Dies ist nützlich für die Implementierung der Eigenschaften, die indiziert oder parametrisiert werden.

### <a name="example"></a>Beispiel

Betrachten Sie die folgende Deklaration der Get und -Member-Funktionen, die der Benutzer einer bestimmten Zeile und Spalte angefordert wird, wenn die Eigenschaft zugreifen können:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Diese entsprechen den folgenden DISP_PROPERTY_PARAM-Makro in die Dispatchzuordnung Steuerelement:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

Wenn Sie beispielsweise sollten Sie die folgende Get und -Member Funktionen:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Diese entsprechen den folgenden DISP_PROPERTY_PARAM-Makro in die Dispatchzuordnung Steuerelement:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="disp_defvalue"></a>  DISP_DEFVALUE

Wird einer vorhandenen Eigenschaft den Standardwert eines Objekts an.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
Der Name der Klasse.

*pszName*<br/>
Externer Name der Eigenschaft, die die "Value" des Objekts darstellt.

### <a name="remarks"></a>Hinweise

Ein Standardwert macht das Programmieren von des Automatisierungsobjekts für Visual Basic-Anwendungen.

Der "Default Value" des Objekts ist die Eigenschaft, die abgerufen oder festgelegt werden, wenn ein Verweis auf ein Objekt eine Eigenschaft oder das Member-Funktion nicht angegeben wird.

### <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
