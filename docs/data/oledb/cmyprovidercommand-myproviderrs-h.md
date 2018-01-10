---
title: CMyProviderCommand (MyProviderRS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67a394ce3c3b05e3f5eea49cbd3a234a0dd89df2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand (MyProviderRS.H)
Die `CMyProviderCommand` Klasse ist die Implementierung für die Anbieter-Befehlsobjekt. Sie stellt die Implementierung für die `IAccessor`, `ICommandText`, und **ICommandProperties** Schnittstellen. Die `IAccessor` Schnittstelle ist identisch mit der im Rowset. Das Befehlsobjekt verwendet die Zugriffsmethode, um Bindungen für Parameter anzugeben. Das Rowsetobjekt, das verwendet werden, um Bindungen für Ausgabespalten anzugeben. Die `ICommandText` Schnittstelle ist eine gute Möglichkeit, einen Textbefehl anzugeben. Dieses Beispiel verwendet die `ICommandText` Schnittstelle später, wenn sie benutzerdefinierten Code hinzufügt, überschreibt auch die `ICommand::Execute` Methode. Die **ICommandProperties** Schnittstelle behandelt alle Eigenschaften für die Befehls- und Rowsetobjekte-Objekte.  
  
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
  
 Die `IAccessor` Schnittstelle verwaltet alle Bindungen, die bei der Befehle und Rowsets verwendet. Der Consumer ruft **IAccessor:: CreateAccessor** mit einem Array von **DBBINDING** Strukturen. Jede **DBBINDING** Struktur enthält die Informationen darüber, wie die spaltenbindungen (z. B. Typ und Länge) behandelt werden sollen. Der Anbieter empfängt die Strukturen und bestimmt dann, wie die Daten übertragen werden sollen, und gibt an, ob eine Konvertierung erforderlich sind. Die `IAccessor` -Schnittstelle im Befehlsobjekt verwendet, um alle Parameter im Befehl zu behandeln.  
  
 Das Command-Objekt stellt auch eine Implementierung von `IColumnsInfo`. OLE DB benötigt die `IColumnsInfo` Schnittstelle. Die Schnittstelle ermöglicht es, Abrufen von Informationen zu den Parametern des Befehls. Das Rowsetobjekt verwendet die `IColumnsInfo` -Schnittstelle zur Rückgabe von Informationen zu den Ausgabespalten an den Anbieter.  
  
 Der Anbieter enthält auch eine Schnittstelle mit dem Namen `IObjectWithSite`. Die `IObjectWithSite` Schnittstelle wurde in ATL 2.0 implementiert und ermöglicht es dem Implementierer Informationen über sich selbst an den untergeordneten übergeben. Das Befehlsobjekt verwendet die `IObjectWithSite` Informationen anzuweisen, alle generierten Rowset-Objekte, die sie erstellt wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)