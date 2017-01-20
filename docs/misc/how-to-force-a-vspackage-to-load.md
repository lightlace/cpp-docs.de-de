---
title: "Gewusst wie: Erzwingen eines VSPackage-Ladevorgangs"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VSPackages, Erzwingen des Ladevorgangs"
  - "VSPackages, laden"
ms.assetid: 05f4dc3f-3c9a-45ea-96da-986553b5c5f2
caps.latest.revision: 20
caps.handback.revision: "20"
manager: "douge"
---
# Gewusst wie: Erzwingen eines VSPackage-Ladevorgangs
normalerweise nur VSPackages geladen werden, wenn sich ihre zugehörigen Funktionen erforderlich ist, einen Vorgang abzuschließen.  Unter bestimmten Umständen kann ein VSPackage muss jedoch VSPackages geladen werden soll, ein anderes erzwingen.  Zum Beispiel könnte ein größeres VSPackage Leichtgewichtler Programmierung in einem VSPackage Kontext nicht als CMDUIContext verfügbar ist.  
  
 Sie können die <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage*>\-Methode verwenden, um zu erzwingen, dass VSPackages geladen werden soll.  
  
### So erzwingen Sie VSPackages zu ladende  
  
-   Fügen Sie diesen Code in die <xref:Microsoft.VisualStudio.Shell.Package.Initialize*> VSPackages Methode ein, die ein anderes VSPackage erzwingt, um zu laden:  
  
     [!CODE [ForceVSPackageLoad#01](../CodeSnippet/VS_Snippets_VSSDK/forcevspackageload#01)]  
  
     Wenn ein VSPackage initialisiert wird, erzwingt dies `PackageToBeLoaded` , um zu laden.  
  
## Robuste Programmierung  
 Laden aktiviert sollte nicht für VSPackage\-Kommunikation verwendet werden.  Verwenden Sie stattdessen [Verwendung und Bereitstellung von Diensten](../Topic/Using%20and%20Providing%20Services.md).  
  
## Siehe auch  
 [Verwalten von VSPackages](../Topic/Managing%20VSPackages.md)   
 [VSPackages](../Topic/VSPackages.md)