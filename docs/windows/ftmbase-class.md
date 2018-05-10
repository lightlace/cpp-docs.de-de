---
title: FtmBase-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
dev_langs:
- C++
helpviewer_keywords:
- FtmBase class
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7bcc003811a747569f22f6b2603faf72096dd049
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="ftmbase-class"></a>FtmBase-Klasse
Stellt ein Freethread-Marshaller-Objekt dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,   
   Microsoft::WRL::CloakedIid<IMarshal> >;  
```  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie im Thema "IMarshal" in der "COM-Schnittstellen" des Themas im Thema "COM-Verweis" in der MSDN Library.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[FtmBase::FtmBase-Konstruktor](../windows/ftmbase-ftmbase-constructor.md)|Initialisiert eine neue Instanz der FtmBase-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[FtmBase::CreateGlobalInterfaceTable-Methode](../windows/ftmbase-createglobalinterfacetable-method.md)|Erstellt eine globale Schnittstellentabelle (GIT).|  
|[FtmBase::DisconnectObject-Methode](../windows/ftmbase-disconnectobject-method.md)|Zwangsweise frei alle externen Verbindungen zu einem Objekt. Die Objekt-Server Ruft das Objekt Implementierung dieser Methode vor dem Herunterfahren.|  
|[FtmBase::GetMarshalSizeMax-Methode](../windows/ftmbase-getmarshalsizemax-method.md)|Rufen Sie die obere Grenze für die Anzahl der Bytes, die erforderlich sind, um den angegebenen Schnittstellenzeiger auf das angegebene Objekt zu marshallen.|  
|[FtmBase::GetUnmarshalClass-Methode](../windows/ftmbase-getunmarshalclass-method.md)|Ruft die CLSID, die COM verwendet, um die DLL, die den Code für den entsprechenden Proxy zu suchen. COM lädt diese DLL aus, um eine nicht initialisierte Instanz des Proxys zu erstellen.|  
|[FtmBase::MarshalInterface-Methode](../windows/ftmbase-marshalinterface-method.md)|Schreibt in einen Stream der Daten, die erforderlich sind, um eine Proxy-Objekt in einem Clientprozess zu initialisieren.|  
|[FtmBase::ReleaseMarshalData-Methode](../windows/ftmbase-releasemarshaldata-method.md)|Zerstört ein gemarshalltes Datenpaket.|  
|[FtmBase:::UnmarshalInterface-Methode](../windows/ftmbase-unmarshalinterface-method.md)|Initialisiert einen neu erstellten Proxy, und gibt einen Schnittstellenzeiger, der diesem Proxy zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[FtmBase::marshaller_-Datenmember](../windows/ftmbase-marshaller-data-member.md)|Enthält einen Verweis auf die freethreaded Marshaller an.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `FtmBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)