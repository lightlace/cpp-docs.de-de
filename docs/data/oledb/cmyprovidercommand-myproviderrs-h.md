---
title: "CMyProviderCommand (MyProviderRS.H)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "cmyprovidercommand"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderCommand Klasse in MyProviderRS.H"
  - "OLE DB-Anbieter, Assistentengenerierte Dateien"
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderCommand (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMyProviderCommand`\-Klasse ist die Implementierung für das Befehlsobjekt des Anbieters.  Sie stellt die Implementierung für die Schnittstellen `IAccessor`, `ICommandText` und **ICommandProperties** bereit.  Die `IAccessor`\-Schnittstelle ist identisch mit der im Rowset enthaltenen Schnittstelle.  Das Befehlsobjekt verwendet den Accessor, um Parameterbindungen festzulegen.  Das Rowsetobjekt verwendet sie, um Bindungen für Ausgabespalten festzulegen.  Die `ICommandText`\-Schnittstelle bietet eine effiziente Möglichkeit, einen Textbefehl anzugeben.  Wenn später benutzerdefinierter Code hinzugefügt wird, wird in diesem Beispiel die `ICommandText`\-Schnittstelle verwendet. Darüber hinaus wird die `ICommand::Execute`\-Methode überschrieben.  Die **ICommandProperties**\-Schnittstelle ist für die Verwaltung sämtlicher Befehls\- und Rowset\-Objekteigenschaften zuständig.  
  
```  
// CMyProviderCommand  
class ATL_NO_VTABLE CMyProviderCommand :   
class ATL_NO_VTABLE CMyProviderCommand :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IAccessorImpl<CMyProviderCommand>,  
   public ICommandTextImpl<CMyProviderCommand>,  
   public ICommandPropertiesImpl<CMyProviderCommand>,  
   public IObjectWithSiteImpl<CMyProviderCommand>,  
   public IConvertTypeImpl<CMyProviderCommand>,  
   public IColumnsInfoImpl<CMyProviderCommand>  
```  
  
 Durch die `IAccessor`\-Schnittstelle werden alle in Befehlen und Rowsets verwendeten Bindungen verwaltet.  Der Consumer ruft **IAccessor::CreateAccessor** mit einem Array von **DBBINDING**\-Strukturen auf.  Jede **DBBINDING**\-Struktur enthält Informationen dazu, wie Spaltenbindungen \(wie Typ und Länge\) zu behandeln sind.  Der Anbieter empfängt die Strukturen und entscheidet dann, auf welche Weise die Daten übertragen werden und ob Konvertierungen notwendig sind.  Die `IAccessor`\-Schnittstelle wird im Befehlsobjekt verwendet, um alle im Befehl enthaltenen Parameter zu behandeln.  
  
 Zusätzlich stellt das Befehlsobjekt eine Implementierung von `IColumnsInfo` bereit.  OLE DB benötigt die `IColumnsInfo`\-Schnittstelle.  Diese Schnittstelle ermöglicht es dem Consumer, Parameterinformationen vom Befehl abzurufen.  Das Rowsetobjekt verwendet die `IColumnsInfo`\-Schnittstelle, um Informationen über die Ausgabespalten an den Anbieter zurückzugeben.  
  
 Der Anbieter verfügt auch über eine Schnittstelle mit dem Namen `IObjectWithSite`.  Die `IObjectWithSite`\-Schnittstelle wurde in ATL 2.0 implementiert und ermöglicht es dem implementierenden Objekt, Informationen über sich selbst an sein untergeordnetes Objekt zu übergeben.  Das Befehlsobjekt verwendet die `IObjectWithSite`\-Informationen, um allen generierten Rowsetobjekten mitzuteilen, von welchem Objekt sie erstellt wurden.  
  
## Siehe auch  
 [Vom Anbieter\-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)