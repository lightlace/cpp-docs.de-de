---
title: "SimpleClassFactory::CreateInstance-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleClassFactory::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance-Methode"
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleClassFactory::CreateInstance-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Instanz die angegebene Schnittstelle.  
  
## Syntax  
  
```  
  
STDMETHOD(  
   CreateInstance  
)  
   (_Inout_opt_ IUnknown* pUnkOuter,   
   REFIID riid,   
   _Deref_out_ void** ppvObject);  
```  
  
#### Parameter  
 `pUnkOuter`  
 Muss `nullptr`; andernfalls ist der Rückgabewert CLASS\_E\_NOAGGREGATION.  
  
 SimpleClassFactory unterstützt keine Aggregation.  Wenn Aggregation unterstützt wurden und das Objekt, das erstellt wurde, Teil eines Aggregats wäre, würde `pUnkOuter` ein Zeiger zur steuernden IUnknown\-Schnittstelle des Aggregats sein.  
  
 `riid`  
 Schnittstellen\-ID des Objekts zu erstellen.  
  
 `ppvObject`  
 Wenn dieser Vorgang abgeschlossen hat, wurden Zeiger auf eine Instanz des Objekts durch den Parameter `riid` an.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Wenn \_\_WRL\_STRICT definiert wird, wird ein Assertionsfehler, ausgegeben, wenn die Basisklasse, die im Klassenvorlagenparameter angegeben ist, nicht von [RuntimeClass](../windows/runtimeclass-class.md) abgeleitet wird, oder wird nicht mit dem ClassicCom Enumerationswert oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) konfiguriert.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [SimpleClassFactory\-Klasse](../windows/simpleclassfactory-class.md)