---
title: "Gewusst wie: Abrufen eines Diensts vom DTE-Objekt"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Dienste, des DTE-Objekts"
ms.assetid: c26a51d4-86f0-454b-9625-5443e55eec7d
caps.latest.revision: 13
caps.handback.revision: "13"
manager: "douge"
---
# Gewusst wie: Abrufen eines Diensts vom DTE-Objekt
Ein Dienst kann von jedem Programm abgerufen werden, das über [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Zugriff auf das <xref:EnvDTE.DTEClass>\-Objekt verfügt.  Beispielsweise können Sie den Assistenten aus einem Dienst <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> vom DTE\-Objekt zugreifen.  Sie können diesen Dienst verwenden, um zum Aktivitätsprotokoll zu schreiben.  Weitere Informationen finden Sie unter [Gewusst wie: Verwenden Sie das Aktivitätsprotokoll](../Topic/How%20to:%20Use%20the%20Activity%20Log.md).  
  
 Das DTE\-Objekt implementiert <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>, die Sie verwenden können, um für einen Dienst aus verwaltetem Code abfragen, indem Sie <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService*>verwenden.  
  
### Um einen Dienst vom DTE\-Objekt abrufen  
  
1.  Der folgende Code erstellt <xref:Microsoft.VisualStudio.Shell.ServiceProvider> vom DTE\-Objekt und ruft <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService*> mit dem Typ des <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> Dienstes an.  Der Dienst wird auf die Schnittstelle umgewandelt <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>, die verwendet wird, um einen Eintrag im Aktivitätsprotokoll zu schreiben.  Weitere Informationen abou, wie zum Aktivitätsprotokoll finden Sie unter schreibt [Gewusst wie: Verwenden Sie das Aktivitätsprotokoll](../Topic/How%20to:%20Use%20the%20Activity%20Log.md).  
  
     [!CODE [GetAServiceFromTheDTEObject#1](../CodeSnippet/VS_Snippets_VSSDK/getaservicefromthedteobject#1)]  
  
## Siehe auch  
 [Verwendung und Bereitstellung von Diensten](../Topic/Using%20and%20Providing%20Services.md)   
 [Service – Grundlagen](../Topic/Service%20Essentials.md)