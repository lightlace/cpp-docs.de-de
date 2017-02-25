---
title: "Festlegen von Eigenschaften f&#252;r Zugriffstasten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstasteneigenschaften"
  - "Eigenschaften [C++], Eigenschaften für Zugriffstasten"
  - "Type-Eigenschaft"
  - "Key-Eigenschaft"
  - "Modifier-Eigenschaft"
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Festlegen von Eigenschaften f&#252;r Zugriffstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In Visual C++ .NET können Sie Eigenschaften für Zugriffstasten festlegen, der [Eigenschaftenfenster](../Topic/Properties%20Window.md) zu einem beliebigen Zeitpunkt. Sie können zudem den Tastenkombinations-Editor verwenden, um die Tastenkombinationseigenschaften in der Tastenkombinationstabelle zu ändern. Mithilfe des Fensters „Eigenschaften“ oder des Tastenkombinations-Editors vorgenommene Änderungen führen zum gleichen Ergebnis: Die Bearbeitungen werden sofort in der Tastenkombinationstabelle berücksichtigt.  
  
 Es gibt drei Eigenschaften für jede Zugriffstaste [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   Die [Modifier-Eigenschaft](../windows/accelerator-modifier-property.md) Steuerungstastenkombinationen für die Zugriffstaste.  
  
    > [!NOTE]
    >  Im Fenster „Eigenschaften“ wird diese Eigenschaft in Form von drei getrennten booleschen Werten angezeigt, wobei alle davon unabhängig gesteuert werden können: ALT, STRG und die UMSCHALTTASTE.  
  
-   Die [Schlüsseleigenschaft](../windows/accelerator-key-property.md) wird die eigentliche Taste als Zugriffstaste verwenden.  
  
-   Die [Type-Eigenschaft](../windows/accelerator-type-property.md) bestimmt, ob der Schlüssel als virtuelle (VIRTKEY) oder als ASCII/ANSI interpretiert wird.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md)   
 [Ressourcen-Editoren](../mfc/resource-editors.md)   
 [Zugriffstasten-Editor](../mfc/accelerator-editor.md)