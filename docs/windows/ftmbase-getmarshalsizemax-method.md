---
title: "FtmBase::GetMarshalSizeMax-Methode"
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
  - "ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMarshalSizeMax-Methode"
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::GetMarshalSizeMax-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rufen Sie die Obergrenze für die Anzahl von Bytes erforderlich, um den angegebenen Schnittstellenzeiger auf dem angegebenen Objekt zu marshallen ab.  
  
## Syntax  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### Parameter  
 `riid`  
 Verweis auf den Bezeichner der gemarshallt werden Schnittstelle.  
  
 `pv`  
 Gemarshallt werden Schnittstellenzeiger; kann NULL sein.  
  
 `dwDestContext`  
 Zielkontext, bei dem die angegebene Schnittstelle das Marshalling rückgängig gemacht werden soll.  
  
 Geben Sie ein oder mehrere MSHCTX\-Enumerationswerten an.  
  
 Zur Zeit kann das Marshalling rückgängig machen entweder in einem anderen Apartment des aktuellen Prozesses \(MSHCTX\_INPROC\) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess \(MSHCTX\_LOCAL\) auftreten.  
  
 `pvDestContext`  
 Für zukünftige Verwendung reserviert; NULL sein muss.  
  
 `mshlflags`  
 Kennzeichnen Sie die Angabe, ob die Daten soll wieder im Clientprozess gesendet werden \- der typische Fall \- oder gemarshallt wird, das auf einen globalen Tabelle geschrieben wird, der von mehreren Clients abgerufen werden kann.  Geben Sie ein oder mehrere MSHLFLAGS\-Enumerationswerten an.  
  
 `pSize`  
 Wenn dieser Vorgang abgeschlossen, Zeiger zur Obergrenze für die Anzahl der zum Marshallingsstream zu schreibenden Daten.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls E\_FAIL oder E\_NOINTERFACE.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)