---
title: Befehlszuordnungen für DHTML-Bearbeitungsbefehle
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 7f420619983283c225ca8fca23c5ea349def1d1b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776153"
---
# <a name="dhtml-editing-command-maps"></a>Befehlszuordnungen für DHTML-Bearbeitungsbefehle

Die folgenden Makros können verwendet werden, um die DHTML-Bearbeitungsbefehle in zuordnen [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-abgeleiteten Klassen. Ein Beispiel ihrer Verwendung finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="dhtml-editing-command-map-macros"></a>DHTML-Bearbeitung für den Befehl Ereigniszuordnungs-Makros

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Deklariert eine Zuordnung DHTML editing-Befehl in einer Klasse.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Startet die Definition einer Zuordnung DHTML editing-Befehl innerhalb einer Klasse.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Markiert das Ende einer DHTML-Bearbeitung Befehl Zuordnung.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Ordnet eine Befehls-ID einen HTML-Befehl.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Ordnet eine Befehls-ID in eine HTML-Bearbeitung-Befehl und die Message-Handler.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Ordnet eine Befehls-ID in eine HTML-Bearbeitung-Befehl und das Element der Debuggerbenutzeroberfläche befindet.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Ordnet eine Befehls-ID eine HTML-Bearbeitungsoberfläche, Command, -Message-Handler und Element der Debuggerbenutzeroberfläche befindet.|

##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP

Deklariert eine Zuordnung DHTML editing-Befehl in einer Klasse.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parameter

*className*<br/>
Der Name der Klasse.

### <a name="remarks"></a>Hinweise

Dieses Makro wird in der Definition der zu verwendende [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-abgeleiteten Klassen.

Verwendung [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) die Zuordnung zu implementieren.

### <a name="example"></a>Beispiel

Finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP

Startet die Definition einer Zuordnung DHTML editing-Befehl innerhalb einer Klasse.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parameter

*className*<br/>
Der Name der Klasse, die die DHTML-Bearbeitung Befehl Zuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) und enthalten die [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) Makro innerhalb der Klassendefinition.

### <a name="remarks"></a>Hinweise

Hinzufügen einer DHTML-Bearbeitung Befehl Zuordnung auf die Klasse, um die Befehle zum Bearbeiten von HTML-Befehlen der Benutzeroberfläche zuordnen.

Platzieren Sie die BEGIN_DHTMLEDITING_CMDMAP-Makro in der Klasse Implementierungsdatei (.cpp) gefolgt von [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) Makros für die Befehle, die die Klasse ist (z. B. von ID_EDIT_CUT zu IDM_CUT) zuordnen. Verwenden der [begin_dhtmlediting_cmdmap](#end_dhtmlediting_cmdmap) Makro, um das Ende der ereigniszuordnung zu markieren.

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

##  <a name="end_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP

Markiert das Ende einer DHTML-Bearbeitung Befehl Zuordnung.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Hinweise

Verwendung mit [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).

### <a name="example"></a>Beispiel

Finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY

Ordnet eine Befehls-ID einen HTML-Befehl.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID (z. B. ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Die HTML-Befehl aus, um die Bearbeitung *CmdID* (z. B. IDM_COPY) zugeordnet.

### <a name="example"></a>Beispiel

Finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC

Ordnet eine Befehls-ID in eine HTML-Bearbeitung-Befehl und die Message-Handler.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID (z. B. ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Die HTML-Befehl aus, um die Bearbeitung *CmdID* (z. B. IDM_COPY) zugeordnet.

*member_func_name*<br/>
Der Name der Meldungshandler-Funktion, die der Befehl zugeordnet ist.

### <a name="example"></a>Beispiel

Finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE

Ordnet eine Befehls-ID in eine HTML-Bearbeitung-Befehl und das Element der Debuggerbenutzeroberfläche befindet.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID (z. B. ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Die HTML-Befehl aus, um die Bearbeitung *CmdID* (z. B. IDM_COPY) zugeordnet.

*elemType*<br/>
Das Element vom Benutzeroberflächentyp; einer der AFX_UI_ELEMTYPE_NORMAL AFX_UI_ELEMTYPE_CHECKBOX oder AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Beispiel

Finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

Ordnet eine Befehls-ID eine HTML-Bearbeitungsoberfläche, Command, -Message-Handler und Element der Debuggerbenutzeroberfläche befindet.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Parameter

*cmdID*<br/>
Die Befehls-ID (z. B. ID_EDIT_COPY).

*dhtmlcmdID*<br/>
Die HTML-Befehl aus, um die Bearbeitung *CmdID* (z. B. IDM_COPY) zugeordnet.

*member_func_name*<br/>
Der Name der Meldungshandler-Funktion, die der Befehl zugeordnet ist.

*elemType*<br/>
Das Element vom Benutzeroberflächentyp; einer der AFX_UI_ELEMTYPE_NORMAL AFX_UI_ELEMTYPE_CHECKBOX oder AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Beispiel

Finden Sie unter [HTMLEdit Beispiel](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxhtml.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
