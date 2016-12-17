---
title: "FtmBase::MarshalInterface-Methode"
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
  - "ftm/Microsoft::WRL::FtmBase::MarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MarshalInterface-Methode"
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::MarshalInterface-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schreibt in einen Stream die Daten, die erforderlich sind, um ein in einem Proxyobjekt Clientprozess zu initialisieren.  
  
## Syntax  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### Parameter  
 `pStm`  
 Zeiger zum während des Marshallens Stream, verwendet werden.  
  
 `riid`  
 Verweis auf den Bezeichner der gemarshallt werden Schnittstelle.  Diese Schnittstelle muss von der IUnknown\-Schnittstelle abgeleitet werden.  
  
 `pv`  
 Zeiger zum gemarshallt werden Schnittstellenzeiger; kann NULL sein, wenn der Aufrufer einen Zeiger nicht zur gewünschten Schnittstelle ist.  
  
 `dwDestContext`  
 Zielkontext, bei dem die angegebene Schnittstelle das Marshalling rückgängig gemacht werden soll.  
  
 Geben Sie ein oder mehrere MSHCTX\-Enumerationswerten an.  
  
 Unmarshalling kann in einem anderen Apartment des aktuellen Prozesses \(MSHCTX\_INPROC\) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess \(MSHCTX\_LOCAL\) auftreten.  
  
 `pvDestContext`  
 Für die zukünftige Verwendung reserviert. Muss 0 \(null\) sein.  
  
 `mshlflags`  
 Gibt an, ob die Daten soll wieder im Clientprozess gesendet werden \- der typische Fall \- oder gemarshallt wird, das auf einen globalen Tabelle geschrieben wird, der von mehreren Clients abgerufen werden kann.  
  
## Rückgabewert  
 S\_OK  
 Der von Schnittstellenzeigern wurde erfolgreich gemarshallt.  
  
 E\_NOINTERFACE  
 Die angegebene Schnittstelle wird nicht unterstützt.  
  
 STG\_E\_MEDIUMFULL  
 Der Stream ist voll.  
  
 E\_FAIL  
 Fehler beim Vorgang.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)