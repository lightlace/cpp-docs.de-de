---
title: "ICommandSource Interface"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ICommandSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandSource interface"
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandSource Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet die Befehle, die von einem Befehlsquellenobjekt zu einem Benutzersteuerelement gesendet werden.  
  
## Syntax  
  
```  
interface class ICommandSource  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](../Topic/ICommandSource::AddCommandHandler.md)|Fügt einen Befehlshandler einem Befehlsquellenobjekt hinzu.|  
|[ICommandSource::AddCommandRangeHandler](../Topic/ICommandSource::AddCommandRangeHandler.md)|Fügt eine Gruppe Befehlshandler einem Befehlsquellenobjekt hinzu.|  
|[ICommandSource::AddCommandRangeUIHandler](../Topic/ICommandSource::AddCommandRangeUIHandler.md)|Fügt eine Gruppe Meldungshandler für Benutzeroberflächenbefehle einem Befehlsquellenobjekt hinzu.|  
|[ICommandSource::AddCommandUIHandler](../Topic/ICommandSource::AddCommandUIHandler.md)|Fügt einen Meldungshandler für Benutzeroberflächenbefehle einem Befehlsquellenobjekt hinzu.|  
|[ICommandSource::PostCommand](../Topic/ICommandSource::PostCommand.md)|Sendet eine Nachricht verarbeitet werden, ohne darauf zu warten.|  
|[ICommandSource::RemoveCommandHandler](../Topic/ICommandSource::RemoveCommandHandler.md)|Entfernt einen Befehlshandler von einem Befehlsquellenobjekt.|  
|[ICommandSource::RemoveCommandRangeHandler](../Topic/ICommandSource::RemoveCommandRangeHandler.md)|Entfernt eine Gruppe Befehlshandler von einem Befehlsquellenobjekt.|  
|[ICommandSource::RemoveCommandRangeUIHandler](../Topic/ICommandSource::RemoveCommandRangeUIHandler.md)|Entfernt eine Gruppe Meldungshandler für Benutzeroberflächenbefehle von einem Befehlsquellenobjekt.|  
|[ICommandSource::RemoveCommandUIHandler](../Topic/ICommandSource::RemoveCommandUIHandler.md)|Entfernt einen Meldungshandler für Benutzeroberflächenbefehle von einem Befehlsquellenobjekt.|  
|[ICommandSource::SendCommand](../Topic/ICommandSource::SendCommand.md)|vor dem Zurückgeben sendet eine Meldung und wartet, verarbeitet werden.|  
  
## Hinweise  
 Wenn Sie ein Benutzersteuerelement in einer MFC\-Ansicht hosten, leitet [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) Befehle und Updatebefehlsbenutzeroberflächenmeldungen zum Benutzersteuerelement, ihr zu ermöglichen, MFC\-Befehle zu behandeln weiter \(beispielsweise, und Symbolleisten\-Schaltflächen\). Dadurch  Mit [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md) implementieren, geben Sie dem Benutzersteuerelement ein Verweis auf `ICommandSource`\-Objekt.  
  
 Unter [Gewusst wie: Hinzufügen von Befehlsrouting zum Windows Forms\-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) finden Sie ein Beispiel zur Verwendung von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Anforderungen  
 **Header:** afxwinforms.h \(definiert in Assembly in \\ atlmfc \\ lib mfcmifc80.dll\)  
  
## Siehe auch  
 [Gewusst wie: Hinzufügen von Befehlsrouting zum Windows Forms\-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget Interface](../../mfc/reference/icommandtarget-interface.md)