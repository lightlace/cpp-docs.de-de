---
title: -GENPROFILE, - FASTGENPROFILE (Profilerstellung instrumentierenden Build generieren) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 028b31044d035def628785969a04c27af4699f65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE, /FASTGENPROFILE (Profilerstellung instrumentierenden Build generieren)
Gibt die Generierung einer PGD-Datei durch den Linker an, um die profilgesteuerte Optimierung (PGO) zu unterstützen.  /GENPROFILE und /FASTGENPROFILE verwenden unterschiedliche Standardparameter. Verwenden Sie /GENPROFILE, um die Genauigkeit der Geschwindigkeit und Speicherauslastung bei der Profilerstellung vorzuziehen. Verwenden Sie /FASTGENPROFILE, um eine geringere Speicherauslastung und eine höhere Geschwindigkeit der Genauigkeit vorzuziehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/{GENPROFILE|FASTGENPROFILE}[:{COUNTER32|COUNTER64|EXACT|MEMMAX=#|MEMMIN=#|NOEXACT|NOPATH|NOTRACKEH|PATH|PGD=filename|TRACKEH}]   
```  
  
## <a name="remarks"></a>Hinweise  
 COUNTER32 &#124; COUNTER64  
 Verwenden Sie COUNTER32, um die Verwendung von 32-Bit- und COUNTER64, um die Verwendung von 64-Bit-Testindikatoren anzugeben. Wenn Sie /GENPROFILE angeben, wird standardmäßig COUNTER64 verwendet. Wenn Sie /FASTGENPROFILE angeben, wird standardmäßig COUNTER32 verwendet.  
  
 GENAUE &#124; NOEXACT  
 Verwenden Sie EXACT, um threadsichere ineinandergreifende Inkremente für Tests anzugeben. NOEXACT gibt ungeschützte Inkrementoperationen für Tests an. Die Standardeinstellung ist NOEXACT.  
  
 MEMMAX=Wert, MEMMIN=Wert  
 Verwenden Sie MEMMAX und MEMMIN, um die maximalen und minimalen Reservierungsgrößen für Trainingsdaten im Arbeitsspeicher anzugeben. Der Wert entspricht der Größe des in Bytes zu reservierenden Arbeitsspeichers.  Standardmäßig werden diese Werte über eine interne Heuristik bestimmt.  
  
 PFAD &#124; NOPATH  
 Verwenden Sie PATH, um einen separaten Satz von PGO-Indikatoren für jeden eindeutigen Pfad zu einer Funktion anzugeben. Verwenden Sie NOPATH, um nur einen Satz von Indikatoren für die einzelnen Funktionen anzugeben.   Wenn Sie /GENPROFILE angeben, ist PATH die Standardeinstellung. Wenn Sie /FASTGENPROFILE angeben, ist NOPATH die Standardeinstellung.  
  
 TRACKEH &#124; NOTRACKEH  
 Gibt an, ob zusätzliche Indikatoren verwendet werden sollen, um eine genaue Anzahl beizubehalten, wenn während des Trainings Ausnahmen ausgelöst werden. Verwenden Sie TRACKEH, um zusätzliche Indikatoren für eine genaue Anzahl anzugeben. Verwenden Sie NOTRACKEH, um einzelne Indikatoren für Code anzugeben, der keine Ausnahmebehandlung verwendet oder keine Ausnahmen in Ihren Trainingsszenarien erkennt.  Wenn Sie /GENPROFILE angeben, ist TRACKEH die Standardeinstellung. Wenn Sie /FASTGENPROFILE angeben, ist NOTRACKEH die Standardeinstellung.  
  
 PGD=Dateiname  
 Gibt einen Basisdateinamen für die PGD-Datei an. Standardmäßig wird vom Linker der Name der ausführbaren Basisbilddatei mit der Erweiterung PGD verwendet.  
  
 Die Optionen /GENPROFILE und /FASTGENPROFILE weisen den Linker an, die zur Unterstützung des Anwendungstrainings für die profilgesteuerte Optimierung (PGO) erforderliche Datei zum Instrumentieren der Profilerstellung zu generieren. Die vom Anwendungstraining generierten Informationen zur Profilerstellung werden als Eingabe verwendet, um während der Builderstellung Zieloptimierungen für vollständige Programme durchzuführen.   Sie können zusätzliche Optionen festlegen, um die verschiedenen Features für die Profilerstellung während des App-Trainings und der App-Erstellung hinsichtlich der Leistung zu steuern. Die durch /GENPROFILE angegebenen Standardoptionen erzielen die genauesten Ergebnisse, insbesondere bei großen, komplexen Multithread-Apps. Die /FASTGENPROFILE-Option verwendet unterschiedliche Standardwerte für einen geringeren Speicherbedarf und höhere Geschwindigkeiten während des Trainings, was zu Lasten der Genauigkeit geht.  
  
 Informationen zur Profilerstellung werden beim Ausführen der instrumentierten App erfasst, nachdem der Build mit /GENPROFILE oder /FASTGENPROFILE erstellt wurde. Diese Informationen werden vom Linker verwendet, wenn Sie die /USEPROFILE-Option angeben. Weitere Informationen zum Trainieren Ihrer App und Details zu den erfassten Daten finden Sie unter „Profilgesteuerte Optimierung“.  
  
 Bei der Angabe von /GENPROFILE oder /FASTGENPROFILE müssen Sie zudem /LTCG angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [/ LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md)