---
title: Pgosweep | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c703bc68a36dd21c837e62738d9d2c2631502a0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="pgosweep"></a>pgosweep
Bei profilgesteuerter Optimierung verwendet, um alle Profildaten aus ein aktives Programm in die PGC-Datei zu schreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### <a name="parameters"></a>Parameter  
 `options`  
 Ein optionaler Parameter, der leer gelassen werden kann. Die gültigen Werte für `options` lauten wie folgt:  
  
-   **/?** oder **/Help,** zeigt die Hilfe an.  
  
-   **/ noreset,** behält die Anzahl die in der Common Language Runtime-Datenstrukturen.  
  
 `image`  
 Der vollständige Pfad einer .exe oder .dll-Datei, die mit dem Compiler Option/LTCG: PGINSTRUMENT erstellt wurde.  
  
 `pgcfile`  
 Die PGC-Datei, in dem mit diesem Befehl die Daten Anzahlen schreibt.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Befehl funktioniert auf Programme, die mit der Compileroption/LTCG: PGINSTRUMENT erstellt wurden. Er unterbricht ein aktives Programm, und schreibt die Profildaten zu einer neuen PGC-Datei. Standardmäßig setzt der Befehl Anzahlen nach jedem Schreibvorgang. Bei Angabe der **/noreset** -Option der Befehl Notieren Sie die Werte, aber nicht zurückgesetzt werden sie in der laufenden Anwendung. Diese Option erhalten doppelte Daten Sie, wenn Sie die Profildaten später abrufen.  
  
 Eine alternative Verwendung für `pgosweep` Profilinformationen nur für die Laufzeit der Anwendung abrufen. Sie könnten z. B. ausführen `pgosweep` kurz nach dem Starten der Anwendung und verwerfen die Datei. Dadurch würde Startkosten zugeordnete Profildaten entfernt. Führen Sie Sie dann `pgosweep` vor dem Beenden der Anwendung. Die gesammelten Daten hat jetzt Profilinformationen nur von der Common Language Runtime.  
  
 Wenn Sie benennen eine PGC-Datei (`pgcfile`) können Sie das Standardformat ist *Appname! n*PGC. Wenn Sie dieses Format verwenden, findet der Compiler diese Daten in die/LTCG: PGO-Phase. Wenn Sie das Standardformat nicht verwenden, müssen Sie verwenden [Pgomgr](../../build/reference/pgomgr.md) die PGC-Dateien zusammenzuführen.  
  
## <a name="example"></a>Beispiel  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 In diesem Beispiel `pgosweep` schreibt die aktuellen Profilinformationen für myapp.exe in MyApp! 1.pgc.  
  
## <a name="see-also"></a>Siehe auch  
 [Tools für die manuelle profilgesteuerte Optimierung (PGO)](../../build/reference/tools-for-manual-profile-guided-optimization.md)