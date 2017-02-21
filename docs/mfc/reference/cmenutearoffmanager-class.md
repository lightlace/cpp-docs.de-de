---
title: "CMenuTearOffManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMenuTearOffManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenuTearOffManager class"
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CMenuTearOffManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet Tearoffe Menüs.  Ein Tearoffes Menü ist ein Menü in der Menüleiste.  Der Benutzer kann ein Tearoffes Menü in der Menüleiste entfernen und das Menü Tearoffe bewirken von Fenstern.  
  
## Syntax  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](../Topic/CMenuTearOffManager::CMenuTearOffManager.md)|Erstellt ein `CMenuTearOffManager`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](../Topic/CMenuTearOffManager::Build.md)||  
|[CMenuTearOffManager::GetRegPath](../Topic/CMenuTearOffManager::GetRegPath.md)||  
|[CMenuTearOffManager::Initialize](../Topic/CMenuTearOffManager::Initialize.md)|Initialisiert ein `CMenuTearOffManager`\-Objekt.|  
|[CMenuTearOffManager::IsDynamicID](../Topic/CMenuTearOffManager::IsDynamicID.md)||  
|[CMenuTearOffManager::Parse](../Topic/CMenuTearOffManager::Parse.md)||  
|[CMenuTearOffManager::Reset](../Topic/CMenuTearOffManager::Reset.md)||  
|[CMenuTearOffManager::SetInUse](../Topic/CMenuTearOffManager::SetInUse.md)||  
|[CMenuTearOffManager::SetupTearOffMenus](../Topic/CMenuTearOffManager::SetupTearOffMenus.md)||  
  
## Hinweise  
 Um Tearoffe Menüs in der Anwendung zu verwenden, müssen Sie ein `CMenuTearOffManager`\-Objekt verfügen.  In den meisten Fällen erstellen Sie nicht initialisieren oder ein `CMenuTearOffManager`\-Objekt direkt.  Dies wird für Sie behandelt, wenn Sie die [CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md)\-Funktion aufrufen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CMenuTearOffManager`\-Objekt erstellt und initialisiert, indem die `CWinAppEX::EnableTearOffMenus`\-Methode aufruft.  Dieser Codeausschnitt ist Teil [Word\-Auflagenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#12](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#12)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)  
  
## Anforderungen  
 **Header:** afxmenutearoffmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)