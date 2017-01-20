---
title: "Fehlerbehebung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Fehlerbehebung"
  - "Fehlerbehebung [C++]"
ms.assetid: c509b089-a542-44be-8f22-dc5832967a48
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Fehlerbehebung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei der Datenbindung erfolgt die Fehlerbehebung über Fehlerereignisse oder Fehlerobjekte.  
  
##  <a name="vcreferrortrappingviaerrorevents"></a> Fehlerbehebung über Fehlerereignisse  
 Sowohl ADO\-Datensteuerelemente als auch RDO\-Remote\-Datensteuerelemente verfügen über Fehlerereignisse.  In der Regel definieren Sie einen Fehlerereignishandler.  Die Ereignishandler haben die folgende Signatur.  
  
```  
void CMyDlg::OnErrorAdodc1(long ErrorNumber,  
                           BSTR* FAR Description,  
                           long Scode,  
                           LPCTSTR Source,  
                           LPCTSTR HelpFile,  
                           long HelpContext,  
                           BOOL FAR* fCancelDisplay)  
```  
  
 Das **Description**\-Feld enthält normalerweise einen Eintrag. Die Felder **ErrorNumber** und **Scode** enthalten nur einen Eintrag, wenn COM\-Fehler auftreten.  Der Inhalt des **Description**\-Felds wird durch einen Ereignishandler in einem Meldungsfeld angezeigt.  Beispiel:  
  
```  
{  
   USES_CONVERSION;     
// note: have to include the ATL file ATLConv.h to use the ATL conversion macros  
   ::AfxMessageBox(OLE2T(*Description), MB_OK);  
}  
```  
  
 ADO\-Datensteuerelement und RDO\-Remote\-Datensteuerelement sind jedoch bereits für das Auffangen von Fehlerereignissen konfiguriert, sodass keine Codierung erforderlich ist.  
  
##  <a name="vcreferrortrappingviaerrorobjects"></a> Fehlerbehebung über Fehlerobjekte  
 Sowohl ADO als auch RDO verfügen über Fehlerobjekte.  Beim Generieren von [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md) werden Wrapper für Fehlerobjekte jedoch lediglich vom RDO\-Remote\-Datensteuerelement, nicht aber vom ADO\-Datensteuerelement erstellt.  
  
 Vom ADO\-Datensteuerelement werden automatisch ADO\-Fehlermeldungen angezeigt.  
  
## Siehe auch  
 [Datenbindung mit ActiveX\-Steuerelementen in Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)