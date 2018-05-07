---
title: BEFEHLSZUORDNUNGEN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69630d00b09534d97d5e46a8400b73f0e9d85b24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dhtml-editing-command-maps"></a>Befehlszuordnungen für DHTML-Bearbeitungsbefehle
Die folgenden Makros können verwendet werden, um DHTML-Bearbeitungsbefehle in zuordnen [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-abgeleitete Klassen. Ein Beispiel ihrer Verwendung finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="dhtml-editing-command-map-macros"></a>DHTML-bearbeiten für den Befehl Ereigniszuordnungs-Makros  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Deklariert eine Zuordnung DHTML bearbeitende-Befehl in einer Klasse.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Startet die Definition einer Zuordnung DHTML Bearbeitung Befehl innerhalb einer Klasse.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Markiert das Ende einer Bearbeitung DHTML-Befehl-Zuordnung.|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Ordnet eine Befehls-ID einen HTML-Befehl.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Ordnet eine Befehls-ID in eine HTML-Befehl und die Message-Handler.|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Ordnet eine Befehls-ID auf ein HTML-Befehl und der Benutzeroberflächen-Elements.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Ordnet eine Befehls-ID ein Bearbeiten von Befehl, Message-Handler und Benutzer-Schnittstellenelement HTML.|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP  
 Deklariert eine Zuordnung DHTML bearbeitende-Befehl in einer Klasse.  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird in der Definition der zu verwendende [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-abgeleitete Klassen.  
  
 Verwendung [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) die Zuordnung zu implementieren.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP  
 Startet die Definition einer Zuordnung DHTML Bearbeitung Befehl innerhalb einer Klasse.  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse mit der Bearbeitung DHTML-Befehl-Zuordnung. Diese Klasse sollte direkt oder indirekt aus ableiten [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) und enthalten die [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) Makro innerhalb der Klassendefinition.  
  
### <a name="remarks"></a>Hinweise  
 Die Klasse, um die Befehle zum Bearbeiten von HTML-Benutzeroberflächenbefehlen zuordnen eine Bearbeitung DHTML-Befehl-Karte hinzugefügt.  
  
 Ort der `BEGIN_DHTMLEDITING_CMDMAP` Makros in der Klasse Implementierungsdatei (.cpp), gefolgt von [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) Makros für die Befehle, die die Klasse zugeordnet ist (z. B. von **ID_EDIT_CUT** zu  **IDM_CUT**). Verwenden der [begin_dhtmlediting_cmdmap](#end_dhtmlediting_cmdmap) Makro auf das Ende der ereigniszuordnung zu markieren.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP  
 Markiert das Ende einer Bearbeitung DHTML-Befehl-Zuordnung.  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung in Verbindung mit [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY  
 Ordnet eine Befehls-ID einen HTML-Befehl.  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zugeordnet (z. B. **IDM_COPY**).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC  
 Ordnet eine Befehls-ID in eine HTML-Befehl und die Message-Handler.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zugeordnet (z. B. **IDM_COPY**).  
  
 `member_func_name`  
 Der Name der Nachrichtenhandler Funktion, die der Befehl zugeordnet ist.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE  
 Ordnet eine Befehls-ID auf ein HTML-Befehl und der Benutzeroberflächen-Elements.  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zugeordnet (z. B. **IDM_COPY**).  
  
 `elemType`  
 Der Elementtyp der Schnittstelle an; einer der **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, oder **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 Ordnet eine Befehls-ID ein Bearbeiten von Befehl, Message-Handler und Benutzer-Schnittstellenelement HTML.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zugeordnet (z. B. **IDM_COPY**).  
  
 `member_func_name`  
 Der Name der Nachrichtenhandler Funktion, die der Befehl zugeordnet ist.  
  
 `elemType`  
 Der Elementtyp der Schnittstelle an; einer der **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, oder **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
