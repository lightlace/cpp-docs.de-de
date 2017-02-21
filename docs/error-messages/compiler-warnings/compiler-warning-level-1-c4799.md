---
title: "Compilerwarnung (Stufe 1) C4799 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4799"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4799"
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4799
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Keine EMMS\-Anweisung am Ende von Funktion 'Funktion'  
  
 Die Funktion hat mindestens eine MMX\-Anweisung, aber keine EMMS\-Anweisung.  Wenn eine Multimediaanweisung verwendet wird, sollte auch eine EMMS\-Anweisung verwendet werden, um das Tagwort "Multimedia" am Ende des MMX\-Codes zu löschen.  Weitere Informationen zu EMMS\-Anweisungen finden Sie unter [Richtlinien für die Verwendung von EMMS](assetId:///a0c3b1e4-01a4-419c-a58f-ff1e97dea7d3).  
  
 Bei Verwendung von **ivec.h** kann C4799 ausgegeben werden. Dies weist darauf hin, dass die EMMS\-Anweisung vor der Rückgabe nicht ordnungsgemäß vom Code verarbeitet wird.  In Bezug auf diese Header ist die Warnung nicht gültig.  Sie können sie deaktivieren, indem Sie \_SILENCE\_IVEC\_C47992 in ivec.h definieren.  Sie sollten jedoch beachten, dass dadurch verhindert wird, dass der Compiler zutreffende Warnungen dieses Typs ausgibt.  
  
 Weiterführende Informationen finden Sie unter [MMX\-Befehlssatz von Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).