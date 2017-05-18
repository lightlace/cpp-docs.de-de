---
title: DHTML-Bearbeitungsbefehle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
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
ms.openlocfilehash: 89aa66d3a1e85183baaba21f001b60e080895f7f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-editing-command-maps"></a>Befehlszuordnungen für DHTML-Bearbeitungsbefehle
Die folgenden Makros können zum Zuordnen von DHTML-Bearbeitung von Befehlen in [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-abgeleitete Klassen. Ein Beispiel ihrer Verwendung finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="dhtml-editing-command-map-macros"></a>DHTML-Bearbeitung für den Befehl Zuordnung-Makros  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Deklariert eine Zuordnung DHTML editing-Befehl in einer Klasse.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Startet die Definition einer Zuordnung DHTML editing-Befehl innerhalb einer Klasse.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Markiert das Ende einer DHTML-Bearbeitung Befehl Zuordnung.|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Ordnet eine Befehls-ID einen HTML-Befehl.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Ordnet eine Befehls-ID zu einem HTML-Befehl und Message-Handler.|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Ordnet eine Befehls-ID zu einem HTML-Befehl und ein Element der Benutzeroberfläche.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Ordnet eine Befehls-ID-HTML-Befehls, der Message-Handler und Benutzeroberflächen-Elements bearbeiten.|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP  
 Deklariert eine Zuordnung DHTML editing-Befehl in einer Klasse.  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird in die Definition des zu verwendenden [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-abgeleitete Klassen.  
  
 Verwendung [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) die Zuordnung zu implementieren.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP  
 Startet die Definition einer Zuordnung DHTML editing-Befehl innerhalb einer Klasse.  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Parameter  
 `className`  
 Der Name der Klasse, die die DHTML-Bearbeitung Befehl Zuordnung enthält. Diese Klasse sollte leiten, direkt oder indirekt von [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) und die [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) Makro innerhalb der Klassendefinition.  
  
### <a name="remarks"></a>Hinweise  
 Die Klasse, um die Befehle zum Bearbeiten von HTML-Befehlen der Benutzeroberfläche zuordnen eine DHTML-Bearbeitung Befehl Zuordnung hinzugefügt.  
  
 Ort der `BEGIN_DHTMLEDITING_CMDMAP` -Makro in der Implementierungsdatei (.cpp) der Klasse, gefolgt von [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) Makros für die Befehle, die die Klasse zugeordnet ist (z. B. von **ID_EDIT_CUT** auf **IDM_CUT**). Verwenden der [begin_dhtmlediting_cmdmap](#end_dhtmlediting_cmdmap) Makro, um das Ende der ereigniszuordnung markieren.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP  
 Markiert das Ende einer DHTML-Bearbeitung Befehl Zuordnung.  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>Hinweise  
 In Verbindung mit [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY  
 Ordnet eine Befehls-ID einen HTML-Befehl.  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zuordnet (z. B. **IDM_COPY**).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC  
 Ordnet eine Befehls-ID zu einem HTML-Befehl und Message-Handler.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zuordnet (z. B. **IDM_COPY**).  
  
 `member_func_name`  
 Der Name der Funktion Meldungshandler, die mit dem Befehl zugeordnet ist.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE  
 Ordnet eine Befehls-ID zu einem HTML-Befehl und ein Element der Benutzeroberfläche.  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zuordnet (z. B. **IDM_COPY**).  
  
 `elemType`  
 Der Elementtyp der Schnittstelle an; einer der **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, oder **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 Ordnet eine Befehls-ID-HTML-Befehls, der Message-Handler und Benutzeroberflächen-Elements bearbeiten.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID (z. B. **ID_EDIT_COPY**).  
  
 `dhtmlcmdID`  
 Die HTML-Befehl aus, um die Bearbeitung `cmdID` zuordnet (z. B. **IDM_COPY**).  
  
 `member_func_name`  
 Der Name der Funktion Meldungshandler, die mit dem Befehl zugeordnet ist.  
  
 `elemType`  
 Der Elementtyp der Schnittstelle an; einer der **AFX_UI_ELEMTYPE_NORMAL**, **AFX_UI_ELEMTYPE_CHECKBOX**, oder **AFX_UI_ELEMTYPE_RADIO**.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [HTMLEdit-Beispiel](../../visual-cpp-samples.md).  

### <a name="requirements"></a>Anforderungen  
  **Header** afxhtml.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

