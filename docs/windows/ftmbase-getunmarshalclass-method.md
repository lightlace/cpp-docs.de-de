---
title: "FtmBase::GetUnmarshalClass-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUnmarshalClass-Methode"
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::GetUnmarshalClass-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft CLSID ab, dem COM verwendet, um die DLL zu suchen, die den Code für den entsprechenden Proxy enthält.  COM lädt diese DLL, um eine nicht initialisierte Instanz des Proxytyps zu erstellen.  
  
## Syntax  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### Parameter  
 `riid`  
 Verweis auf den Bezeichner der gemarshallt werden Schnittstelle.  
  
 `pv`  
 Zeiger zur gemarshallt werden Schnittstelle; kann NULL sein, wenn der Aufrufer einen Zeiger nicht zur gewünschten Schnittstelle ist.  
  
 `dwDestContext`  
 Zielkontext, bei dem die angegebene Schnittstelle das Marshalling rückgängig gemacht werden soll.  
  
 Geben Sie ein oder mehrere MSHCTX\-Enumerationswerten an.  
  
 Unmarshalling kann entweder in einem anderen Apartment des aktuellen Prozesses \(MSHCTX\_INPROC\) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess \(MSHCTX\_LOCAL\) auftreten.  
  
 `pvDestContext`  
 Für zukünftige Verwendung reserviert; NULL sein muss.  
  
 `mshlflags`  
 Wenn dieser Vorgang abgeschlossen hat, Zeiger auf, um einen Proxy verwendet werden CLSID im Clientprozess zu erstellen.  
  
 `pCid`  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls S\_FALSE.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)