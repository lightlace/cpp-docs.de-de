---
title: Klasse CUserTool | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserTool
dev_langs:
- C++
helpviewer_keywords:
- CUserTool class
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2e0b082be6aac7314d8251f89b42ed09e44e2f3d
ms.lasthandoff: 02/24/2017

---
# <a name="cusertool-class"></a>CUserTool-Klasse
Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Die **Tools** auf der Registerkarte der **anpassen** (Dialogfeld) ( [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) ermöglicht es dem Benutzer, Benutzertools hinzuzufügen und den Namen, Befehl, Argumente und Ausgangsverzeichnis für jedes benutzertool anzugeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|Zeichnet das Symbol "Benutzer" in einem bestimmten Rechteck.|  
|[CUserTool::GetCommand](#getcommand)|Gibt eine Zeichenfolge mit dem Text des Befehls mit dem Benutzer zugeordnet.|  
|[CUserTool::GetCommandId](#getcommandid)|Gibt die Befehls-ID des Menüelements das Tool Benutzer zurück.|  
|[CUserTool::Invoke](#invoke)|Führt den Befehl mit dem Benutzer zugeordnet.|  
|[CUserTool::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize).)|  
|[CUserTool::SetCommand](#setcommand)|Legt den Befehl mit dem Benutzer zugeordnet.|  
|[CUserTool::SetToolIcon](#settoolicon)|Lädt das Symbol für das Tool, das von der Anwendung, die das Tool zugeordnet.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Lädt das Standardsymbol für ein Tool.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|Die Befehlszeilenargumente für die benutzertool.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Das Ausgangsverzeichnis für das User-Tool.|  
|[CUserTool::m_strLabel](#m_strlabel)|Der Name des Tools, die im Menüelement für das Tool angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Aktivieren von Benutzertools in Ihrer Anwendung finden Sie unter [CUserToolsManager Klasse](../../mfc/reference/cusertoolsmanager-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Tool erstellt eine `CUserToolsManager` -Objekts die `m_strLabel` -Membervariable, und legen Sie die Anwendung, die die benutzertool ausgeführt wird. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#35;](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxusertool.h  
  
##  <a name="a-namecopyicontoclipboarda--cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedrawtoolicona--cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::DrawToolIcon  
 Zeichnet das Symbol "Benutzer" in der Mitte eines angegebenen Rechtecks.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectImage`  
 Gibt die Koordinaten des Bereichs, um das Symbol anzuzeigen.  
  
##  <a name="a-namegetcommanda--cusertoolgetcommand"></a><a name="getcommand"></a>CUserTool::GetCommand  
 Gibt eine Zeichenfolge mit dem Text des Befehls mit dem Benutzer zugeordnet.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf `CString` -Objekt, das den Text des Befehls gehörenden Benutzer enthält.  
  
##  <a name="a-namegetcommandida--cusertoolgetcommandid"></a><a name="getcommandid"></a>CUserTool::GetCommandId  
 Gibt die Befehls-ID des Benutzers Tools zurück.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID des Benutzers Tools.  
  
##  <a name="a-nameinvokea--cusertoolinvoke"></a><a name="invoke"></a>CUserTool::Invoke  
 Führt den Befehl mit dem Benutzer zugeordnet.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Befehl erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) zum Ausführen eines Befehls mit dem Benutzer zugeordnet. Die Funktion schlägt fehl, wenn der Befehl leer ist oder [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) schlägt fehl.  
  
##  <a name="a-nameloaddefaulticona--cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>CUserTool::LoadDefaultIcon  
 Lädt das Standardsymbol für ein Tool.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das geladen-Symbol ( `HICON`), oder `NULL` Wenn das Standardsymbol geladen werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Symbol für ein benutzerdefiniertes Tool aus der ausführbaren Datei des Tools geladen werden kann.  
  
 Überschreiben Sie diese Methode, um eigene Standardsymbol für das Tool angeben.  
  
##  <a name="a-namemstrargumentsa--cusertoolmstrarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments  
 Die Befehlszeilenargumente für die benutzertool.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Zeichenfolge wird an das Tool übergeben, wenn Sie aufrufen [CUserTool::Invoke](#invoke) oder wenn ein Benutzer mit diesem Tool zugeordneten Befehl klickt.  
  
##  <a name="a-namemstrinitialdirectorya--cusertoolmstrinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory  
 Gibt das Ausgangsverzeichnis für das User-Tool.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable gibt das Ausgangsverzeichnis, das in das Tool ausgeführt, beim Aufruf von wird [CUserTool::Invoke](#invoke) oder wenn ein Benutzer mit diesem Tool zugeordneten Befehl klickt.  
  
##  <a name="a-namemstrlabela--cusertoolmstrlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel  
 Die Bezeichnung, die im Menüelement für das Tool angezeigt wird.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="a-nameserializea--cusertoolserialize"></a><a name="serialize"></a>CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetcommanda--cusertoolsetcommand"></a><a name="setcommand"></a>CUserTool::SetCommand  
 Legt die Anwendung, die die benutzertool ausgeführt wird.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszCmd`  
 Gibt die neue Anwendung mit dem Benutzer zugeordnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine neue Anwendung festlegen, die die benutzertool ausgeführt wird. Die Methode zerstört das alte Symbol und ein neues Symbol aus der angegebenen Anwendung lädt. Wenn sie ein Symbol aus der Anwendung geladen werden kann, lädt er das Standardsymbol für ein Tool durch Aufrufen von [CUserTool::LoadDefaultIcon](#loaddefaulticon).  
  
##  <a name="a-namesettoolicona--cusertoolsettoolicon"></a><a name="settoolicon"></a>CUserTool::SetToolIcon  
 Lädt das Symbol für das Tool, das von der Anwendung, die das Tool verwendet.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Symbol geladen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um das Symbol im Menüelement anzuzeigende geladen. Diese Methode sucht das Symbol in der ausführbaren Datei, die das Tool verwendet. Wenn sie nicht über ein Standardsymbol verfügt, wird das Symbol von bereitgestellten [CUserTool::LoadDefaultIcon](#loaddefaulticon) wird stattdessen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md)

