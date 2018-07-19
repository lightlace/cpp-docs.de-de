---
title: CUserTool Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
dev_langs:
- C++
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 925e93afae4682497263eb96832aa466c6034231
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121315"
---
# <a name="cusertool-class"></a>CUserTool-Klasse
Ein Benutzertool ist ein Menüelement, das eine externe Anwendung ausführt. Die **Tools** auf der Registerkarte die **anpassen** (Dialogfeld) ( [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) ermöglicht es dem Benutzer, Benutzertools hinzuzufügen und um anzugeben, der Name, den Befehl, die Argumente, und ursprüngliche Verzeichnis für jedes benutzertool.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|Zeichnet das Werkzeugsymbol Benutzer in einem bestimmten Rechteck.|  
|[CUserTool::GetCommand](#getcommand)|Gibt eine Zeichenfolge mit dem Text des Befehls mit dem Benutzer zugeordnet.|  
|[CUserTool::GetCommandId](#getcommandid)|Gibt die Befehls-ID des Menüelements des Benutzer-Tools zurück.|  
|[CUserTool::Invoke](#invoke)|Führt den Befehl mit dem Benutzer zugeordnet.|  
|[CUserTool::Serialize](#serialize)|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CUserTool::SetCommand](#setcommand)|Legt den Befehl mit dem Benutzer zugeordnet.|  
|[CUserTool::SetToolIcon](#settoolicon)|Lädt das Symbol für das Tool, das aus der Anwendung verknüpft sind, mit dem Tool an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Lädt das Standardsymbol für ein Tool.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|Die Befehlszeilenargumente für das benutzertool.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Das Ausgangsverzeichnis für die benutzertool.|  
|[CUserTool::m_strLabel](#m_strlabel)|Der Name des Tools, die in dem Menüelement, das für das Tool angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über Benutzertools in der Anwendung zu aktivieren, finden Sie unter [CUserToolsManager Klasse](../../mfc/reference/cusertoolsmanager-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Tool aus einem `CUserToolsManager` Objekt, das Festlegen der `m_strLabel` Membervariablen gespeichert, und legen Sie die Anwendung, die die benutzertool ausgeführt wird. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxusertool.h  
  
##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon  
 Zeichnet das Symbol "Benutzer-Tool" in der Mitte eines angegebenen Rechtecks.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *RectImage*  
 Gibt an, die Koordinaten des Bereichs, um das Symbol anzuzeigen.  
  
##  <a name="getcommand"></a>  CUserTool::GetCommand  
 Gibt eine Zeichenfolge mit dem Text des Befehls mit dem Benutzer zugeordnet.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf `CString` Objekt mit dem Text des Befehls mit dem Benutzer zugeordnet.  
  
##  <a name="getcommandid"></a>  CUserTool::GetCommandId  
 Gibt die Befehls-ID des Benutzers Tools zurück.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID dieses Benutzers-Tools.  
  
##  <a name="invoke"></a>  CUserTool::Invoke  
 Führt den Befehl mit dem Benutzer zugeordnet.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Befehl erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) zum Ausführen eines Befehls mit dem Benutzer zugeordnet. Die Funktion fehlschlägt, wenn der Befehl leer ist oder wenn [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) ein Fehler auftritt.  
  
##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon  
 Lädt das Standardsymbol für ein Tool.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das geladene Symbol (HICON) oder NULL, wenn das Symbol "Standard" kann nicht geladen werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn sie ein Symbol für ein benutzerdefiniertes Tool aus der ausführbaren Datei des Tools laden kann.  
  
 Überschreiben Sie diese Methode, um eine eigene Standardsymbol für das Tool angeben.  
  
##  <a name="m_strarguments"></a>  CUserTool::m_strArguments  
 Die Befehlszeilenargumente für das benutzertool.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Zeichenfolge wird an das Tool übergeben, wenn Sie aufrufen [CUserTool::Invoke](#invoke) oder wenn ein Benutzer mit diesem Tool zugeordneten Befehl klickt.  
  
##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory  
 Gibt das Ausgangsverzeichnis für das benutzertool an.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable gibt das Ausgangsverzeichnis, die in das Tool ausgeführt, beim Aufrufen von wird [CUserTool::Invoke](#invoke) oder wenn ein Benutzer mit diesem Tool zugeordneten Befehl klickt.  
  
##  <a name="m_strlabel"></a>  CUserTool::m_strLabel  
 Die Bezeichnung, die in dem Menüelement, das für das Tool angezeigt wird.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="serialize"></a>  CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Ar*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcommand"></a>  CUserTool::SetCommand  
 Legt die Anwendung, die die benutzertool ausgeführt wird.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszCmd*  
 Gibt die neue Anwendung mit dem Benutzer zugeordnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine neue Anwendung festgelegt werden, die die benutzertool ausgeführt wird. Die Methode zerstört das alte Symbol und ein Symbol "Neues" aus der angegebenen Anwendung lädt. Wenn es ein Symbol aus der Anwendung geladen werden kann, lädt er das Standardsymbol für ein Tool durch Aufrufen von [CUserTool::LoadDefaultIcon](#loaddefaulticon).  
  
##  <a name="settoolicon"></a>  CUserTool::SetToolIcon  
 Lädt das Symbol für das Tool, das von der Anwendung, die vom Tool verwendet wird.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Symbol geladen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um das Symbol im Menüelement anzuzeigende geladen. Diese Methode sucht das Symbol in der ausführbaren Datei, die vom Tool verwendet wird. Wenn sie nicht über ein Standardsymbol verfügt, wird das Symbol von bereitgestellten [CUserTool::LoadDefaultIcon](#loaddefaulticon) wird stattdessen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager-Klasse](../../mfc/reference/cusertoolsmanager-class.md)
