---
title: "FtmBase-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FtmBase-Klasse"
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Free\-Threaded Marshaller\-Objekt dar.  
  
## Syntax  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags< WinRtClassicComMix >,   
   Microsoft::WRL::CloakedIid< IMarshal > >;  
```  
  
## Hinweise  
 Weitere Informationen finden Sie, dass das Thema "IMarshal" im "COM\-Schnittstellen\-" Abschnitt des "COM" Thema in der MSDN Library verweisen.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[FtmBase::FtmBase\-Konstruktor](../windows/ftmbase-ftmbase-constructor.md)|Initialisiert eine neue Instanz der FtmBase\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[FtmBase::CreateGlobalInterfaceTable\-Methode](../windows/ftmbase-createglobalinterfacetable-method.md)|Stellt eine globale Schnittstellentabelle \(GIT\) erstellt.|  
|[FtmBase::DisconnectObject\-Methode](../windows/ftmbase-disconnectobject-method.md)|Gibt erzwungen alle externen Verbindungen mit einem Objekt frei.  Der Server des Objekts ruft die Implementierung des Objekts dieser Methode vor dem Herunterfahren auf.|  
|[FtmBase::GetMarshalSizeMax\-Methode](../windows/ftmbase-getmarshalsizemax-method.md)|Rufen Sie die Obergrenze für die Anzahl von Bytes erforderlich, um den angegebenen Schnittstellenzeiger auf dem angegebenen Objekt zu marshallen ab.|  
|[FtmBase::GetUnmarshalClass\-Methode](../windows/ftmbase-getunmarshalclass-method.md)|Ruft CLSID ab, dem COM verwendet, um die DLL zu suchen, die den Code für den entsprechenden Proxy enthält.  COM lädt diese DLL, um eine nicht initialisierte Instanz des Proxytyps zu erstellen.|  
|[FtmBase::MarshalInterface\-Methode](../windows/ftmbase-marshalinterface-method.md)|Schreibt in einen Stream die Daten, die erforderlich sind, um ein in einem Proxyobjekt Clientprozess zu initialisieren.|  
|[FtmBase::ReleaseMarshalData\-Methode](../windows/ftmbase-releasemarshaldata-method.md)|Zerstört ein gemarshalltes Datenpaket.|  
|[FtmBase:::UnmarshalInterface\-Methode](../windows/ftmbase-unmarshalinterface-method.md)|Initialisiert einen neu erstellten Proxy und einen Schnittstellenzeiger zu diesem Proxy zurück.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[FtmBase::marshaller\_\-Datenmember](../windows/ftmbase-marshaller-data-member.md)|Hält einen Verweis auf das Free\-Threaded Marshaller an.|  
  
## Vererbungshierarchie  
 `FtmBase`  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)