---
title: "IDocHostUIHandlerDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDocHostUIHandlerDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDocHostUIHandlerDispatch interface"
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IDocHostUIHandlerDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle zum Analyse\- und Renderingmodul Microsoft HTML.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
interface IDocHostUIHandlerDispatch : IDispatch  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
> [!NOTE]
>  Die Links in der folgenden Tabelle werden den INet\-SDK\-Referenzthemen für die Member der Schnittstelle [IDocUIHostHandler](https://msdn.microsoft.com/en-us/library/aa753260.aspx).  `IDocHostUIHandlerDispatch` hat die gleichen Funktionen, wie **IDocUIHostHandler**, wenn der Unterschied dieses `IDocHostUIHandlerDispatch` ist, eine Dispatchschnittstelle ist, während **IDocUIHostHandler** eine benutzerdefinierte Schnittstelle ist.  
  
|||  
|-|-|  
|[\<caps:sentence id\="tgt7" sentenceid\="bbafd0070a97938421603b1ef8409510" class\="tgtSentence"\>EnableModeless\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753253.aspx)|Aufgerufen von MSHTML\-Implementierung von [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115).  Außerdem aufgerufen, wenn MSHTML modale Benutzeroberfläche anzeigt.|  
|[\<caps:sentence id\="tgt10" sentenceid\="2cfbfb70fe0af79263134b694d06311c" class\="tgtSentence"\>FilterDataObject\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753254.aspx)|Ersuchte um den Host von MSHTML, dem Host ermöglichen, Datenobjekt MSHTMLS zu ersetzen.|  
|[\<caps:sentence id\="tgt12" sentenceid\="715255e2d7f611c97308a373328e19a0" class\="tgtSentence"\>GetDropTarget\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753255.aspx)|Aufgerufen durch MSHTML, wenn es als Ablageziel verwendet wird, um dem Host ermöglichen, alternative [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) anzugeben.|  
|[\<caps:sentence id\="tgt14" sentenceid\="5a51a8633a0d2036f843073d6f35a4af" class\="tgtSentence"\>GetExternal\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753256.aspx)|Aufgerufen durch MSHTML, erhält die der IDispatch\-Schnittstelle des Hosts.|  
|[\<caps:sentence id\="tgt16" sentenceid\="ce27e0c2f7ebb0aaa2f9088818dc8347" class\="tgtSentence"\>GetHostInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753257.aspx)|Ruft die Benutzeroberfläche\-Funktionen von MSHTML\-Host ab.|  
|[\<caps:sentence id\="tgt18" sentenceid\="693bd2149b17c4586cdc167e13e59f0a" class\="tgtSentence"\>GetOptionKeyPath\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753258.aspx)|Gibt den Registrierungsschlüssel zurück, unter dem MSHTML Benutzereinstellungen speichert.|  
|[\<caps:sentence id\="tgt20" sentenceid\="7fce94585b477684cc21a38fe9ee288c" class\="tgtSentence"\>HideUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753259.aspx)|Aufgerufen, wenn MSHTML seine Menüs und Symbolleisten entfernt.|  
|[\<caps:sentence id\="tgt22" sentenceid\="359e4dcbd80b962decf88ef02d66fe14" class\="tgtSentence"\>OnDocWindowActivate\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753261.aspx)|Aufgerufen von MSHTML\-Implementierung von [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[\<caps:sentence id\="tgt24" sentenceid\="8e472d7f3f3064d2ee6fdddd83002b86" class\="tgtSentence"\>OnFrameWindowActivate\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753262.aspx)|Aufgerufen von MSHTML\-Implementierung von [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[\<caps:sentence id\="tgt26" sentenceid\="3fd38deec5e9f4201074e886bfb178a5" class\="tgtSentence"\>ResizeBorder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753263.aspx)|Aufgerufen von MSHTML\-Implementierung von [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[\<caps:sentence id\="tgt28" sentenceid\="2f382ba3de5494d18b20ccfa348f795e" class\="tgtSentence"\>ShowContextMenu\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753264.aspx)|Aufgerufen von MSHTML, um ein Kontextmenü anzuzeigen.|  
|[\<caps:sentence id\="tgt30" sentenceid\="c6978c4c8ab30ae8380439da613bb63c" class\="tgtSentence"\>ShowUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753265.aspx)|Ermöglicht dem Host, um MSHTML\-Menüs und \- Symbolleisten zu ersetzen.|  
|[\<caps:sentence id\="tgt32" sentenceid\="97bfd5aead25a2d9870b38da4b6745cd" class\="tgtSentence"\>TranslateAccelerator\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753266.aspx)|Aufgerufen durch MSHTML, wenn [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) oder [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) aufgerufen wird.|  
|[\<caps:sentence id\="tgt34" sentenceid\="55c20a6fb6b05f6059d72b2854a7d7e2" class\="tgtSentence"\>TranslateUrl\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753267.aspx)|Aufgerufen durch MSHTML, um dem Host Möglichkeit Browserverhalten, das geladen werden URL zu ändern.|  
|[\<caps:sentence id\="tgt36" sentenceid\="8fdf7c2c3ebf5fa12ecc909279c951ff" class\="tgtSentence"\>UpdateUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753268.aspx)|Benachrichtigt den Host, dass der Befehlszustand geändert hat.|  
  
## Hinweise  
 Ein Host kann die Menüs, Symbolleisten und die Kontextmenüs ersetzen, die von dem Analyse\- und Renderingmodul Microsoft HTML \(MSHTML\) verwendet werden mithilfe der diese Schnittstelle implementiert.  
  
## Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL\-Datei oder C\+\+, wie unten verfügbar.  
  
|Definitionstyp|Datei|  
|--------------------|-----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(auch enthaltene ATLBase.h\)|  
  
## Siehe auch  
 [IDocUIHostHandler](https://msdn.microsoft.com/en-us/library/aa753260.aspx)