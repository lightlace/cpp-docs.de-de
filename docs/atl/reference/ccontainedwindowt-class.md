---
title: "CContainedWindowT Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CContainedWindow"
  - "CContainedWindowT"
  - "ATL.CContainedWindowT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContainedWindow class"
  - "CContainedWindowT class"
  - "contained windows"
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CContainedWindowT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein Fenster, das innerhalb eines anderen Objekts enthalten ist.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class TBase= CWindow,  
class TWinTraits= CControlWinTraits   
>  
class CContainedWindowT :  
public TBase  
```  
  
#### Parameter  
 *TBase*  
 Die Basisklasse der neuen Klasse.  Die standardmäßige Basisklasse ist `CWindow`.  
  
 `TWinTraits`  
 Eine Merkmalklasse, die Stile für das Fenster definiert.  Der Standardwert ist `CControlWinTraits`.  
  
> [!NOTE]
>  [CContainedWindow](../Topic/CContainedWindow.md) ist eine Spezialisierung von `CContainedWindowT`.  Wenn Sie die Basisklasse oder Features ändern möchten, verwenden Sie `CContainedWindowT` direkt.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](../Topic/CContainedWindowT::CContainedWindowT.md)|Konstruktor.  Initialisiert Datenmember, um anzugeben, welche Meldungszuordnung die enthaltenen Meldungen des Fensters verarbeitet.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CContainedWindowT::Create](../Topic/CContainedWindowT::Create.md)|Stellt ein Fenster erstellt.|  
|[CContainedWindowT::DefWindowProc](../Topic/CContainedWindowT::DefWindowProc.md)|Stellt das standardmäßige Meldungsverarbeiten bereit.|  
|[CContainedWindowT::GetCurrentMessage](../Topic/CContainedWindowT::GetCurrentMessage.md)|Gibt die aktuelle Meldung zurück.|  
|[CContainedWindowT::RegisterWndSuperclass](../Topic/CContainedWindowT::RegisterWndSuperclass.md)|Registriert die Fensterklasse des übergeordneten Fensters.|  
|[CContainedWindowT::SubclassWindow](../Topic/CContainedWindowT::SubclassWindow.md)|Ordnet ein Fenster unter.|  
|[CContainedWindowT::SwitchMessageMap](../Topic/CContainedWindowT::SwitchMessageMap.md)|Ändert, welche Meldungszuordnung verwendet wird, um die enthaltenen Meldungen des Fensters zu verarbeiten.|  
|[CContainedWindowT::UnsubclassWindow](../Topic/CContainedWindowT::UnsubclassWindow.md)|Stellt ein zuvor untergeordnetes Fenster wiederher.|  
|[CContainedWindowT::WindowProc](../Topic/CContainedWindowT::WindowProc.md)|\(Statisch\) verarbeitet die Nachrichten, die auf das enthaltende Fenster gesendet werden.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CContainedWindowT::m\_dwMsgMapID](../Topic/CContainedWindowT::m_dwMsgMapID.md)|Identifiziert, welche Meldungszuordnung die enthaltenen Meldungen des Fensters verarbeitet.|  
|[CContainedWindowT::m\_lpszClassName](../Topic/CContainedWindowT::m_lpszClassName.md)|Gibt den Namen einer vorhandenen Fensterklasse an, auf der eine neue Fensterklasse basiert.|  
|[CContainedWindowT::m\_pfnSuperWindowProc](../Topic/CContainedWindowT::m_pfnSuperWindowProc.md)|Punkte an die ursprüngliche Fensterprozedur der Fensterklasse.|  
|[CContainedWindowT::m\_pObject](../Topic/CContainedWindowT::m_pObject.md)|Zeigt auf enthaltenden Objekt.|  
  
## Hinweise  
 `CContainedWindowT` implementiert ein Fenster, das innerhalb eines anderen Objekts enthalten ist.  Die Fensterprozedur von `CContainedWindowT` verwendet eine Meldungszuordnung im enthaltenden Objekt zu den direkten Meldungen zu den zugehörigen Handler.  Wenn Sie ein `CContainedWindowT`\-Objekt erstellen, geben Sie an, welche Meldungszuordnung verwendet werden soll.  
  
 `CContainedWindowT` ermöglicht es Ihnen, ein neues Fenster erstellen, indem Sie eine vorhandene Fensterklasse superclassing.  Die Methode registriert **Create** zuerst eine Fensterklasse, die basierend auf einer vorhandenen Klasse verwendet jedoch `CContainedWindowT::WindowProc` ist.  **Create** erstellt dann ein Fenster auf Grundlage dieser neuen Fensterklasse basiert.  Jede Instanz von `CContainedWindowT` machen übergeordnete Klasse eine andere Fensterklasse ein.  
  
 `CContainedWindowT` unterstützt auch Fenstererstellen von unterklassen.  Die `SubclassWindow`\-Methode fügt ein vorhandenes Fenster zum `CContainedWindowT`\-Objekt an und ändert die Fensterprozedur zu `CContainedWindowT::WindowProc`.  Jede Instanz von `CContainedWindowT` kann ein anderes Fenster unterordnen.  
  
> [!NOTE]
>  Für jedes angegebene Objekt `CContainedWindowT` rufen Sie entweder **Create** oder `SubclassWindow` auf.  Sie sollten beide Methoden auf demselben Objekt nicht aufrufen.  
  
 Wenn Sie die Option **Steuerelement hinzufügen, das auf folgendem basiert** im ATL\-Projekt\-Assistenten verwenden, fügt der Assistent automatisch einen `CContainedWindowT` Datenmember der Klasse hinzu, die das Steuerelement implementiert.  Im folgenden Beispiel wird gezeigt, wie dem Fenster deklariert wird:  
  
 [!CODE [NVC_ATL_Windowing#38](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#38)]  
  
 [!CODE [NVC_ATL_Windowing#39](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#39)]  
  
 [!CODE [NVC_ATL_Windowing#40](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#40)]  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------------------|-----------|  
|Erstellen von Steuerelementen|[ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Verwenden der Fenster in ATL|[ATL\-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL\-Projekt\-Assistent|[Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) und folgende Themen in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## Vererbungshierarchie  
 `TBase`  
  
 `CContainedWindowT`  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap Class](../../atl/reference/cmessagemap-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)