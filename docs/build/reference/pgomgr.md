---
title: Pgomgr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cbb9a4f8b92a1cd495e1312c1aa8a8f77cefcd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pgomgr"></a>pgomgr
Die PGD-Datei hinzugefügt Profildaten aus einer oder mehreren PGC-Dateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### <a name="parameters"></a>Parameter  
 `options`  
 Die folgenden Optionen können für Pgomgr angegeben werden:  
  
 **/ help –**Zeigt Optionen zur Verfügung Pgomgr (Kurzform für /?).  
  
 **/ clear –**bewirkt, dass die PGD-Datei aller Profilinformationen gelöscht werden. Sie können eine PGC nicht angeben Datei wann **/clear** angegeben ist.  
  
 **/ detail**– zeigt detaillierte Statistiken, einschließlich Informationen zum Ausführungsfluss Graph Coverage.  
  
 **/ summary**– zeigt pro Funktion Statistiken.  
  
 **/ eindeutige**– bei Verwendung mit **/summary**, ergänzte Funktionsnamen angezeigt.  Die Standardeinstellung, wenn / eindeutig ist nicht angegeben, wird werden nicht ergänzten Funktionsnamen angezeigt werden.  
  
 **/ merge**[**:***n*]**–**bewirkt, dass die Daten in der PGC-Datei oder die Dateien die PGD-Datei hinzugefügt werden.  Der optionale Parameter  *n* , können Sie angeben, Hat die Daten hinzugefügt werden sollen  *n*  Zeiten.  Angenommen, ein Szenario häufig 6-Mal ausgeführt werden würde, Sie können führen Sie es einmal in einem Testlauf und sechs Mal mit der PGD-Datei hinzufügen **Pgomgr/Merge: 6**.  
  
 `pgcfiles`  
 Eine oder mehrere PGC-Dateien, deren Profil für Daten in die PGD-Datei zusammengeführt werden sollen. Sie können eine einzelne PGC-Datei oder mehrere PGC-Dateien angeben. Wenn Sie keine PGC-Dateien angeben, wird Pgomgr alle PGC-Dateien zusammenführen, deren Dateinamen die PGD-Datei identisch sind.  
  
 `pgdfile`  
 Die PGD-Datei, in der Sie Daten aus Dateien oder PGC-Datei zusammengeführt werden.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]-Eingabeaufforderung aus starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wurde die PGD-Datei von Profildaten gelöscht.  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 Im folgenden Beispiel wurde die Profildaten in myapp1.pgc 3 Mal die PGD-Datei hinzugefügt.  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 Im folgenden Beispiel werden die Datei myapp.pgd Profildaten aus allen "MyApp" # .pgc-Dateien hinzugefügt.  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tools für die manuelle profilgesteuerte Optimierung (PGO)](../../build/reference/tools-for-manual-profile-guided-optimization.md)