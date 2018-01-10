---
title: LINK-Befehlsdateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e585fb8fa11d4e3ffe8eff842baacb05f109754c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="link-command-files"></a>LINK-Befehlsdateien
Sie können Befehlszeilenargumente an LINK in Form einer Befehlsdatei übergeben. Um eine Befehlsdatei an den Linker anzugeben, verwenden Sie die folgende Syntax:  
  
```  
LINK @commandfile  
```  
  
 Die `commandfile` ist der Name einer Textdatei. Keine Leerzeichen oder Tabstopp ist zulässig, zwischen dem at-Zeichen (@) und den Dateinamen. Es ist keine standarderweiterung. Sie müssen den vollständigen Dateinamen, einschließlich eine beliebige Erweiterung angeben. Keine werden Platzhalter verwendet. Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben. LINK verwendet keine Umgebungsvariable für die Datei zu suchen.  
  
 In der Befehlsdatei Argumente können getrennt werden durch Leerzeichen oder Tabstopps (z. B. auf der Befehlszeile) und durch neue Zeilenumbruchzeichen.  
  
 Sie können in einer Befehlsdatei ganz oder teilweise von der Befehlszeile angeben. Sie können mehr als eine Befehlsdatei in einem LINK-Befehl verwenden. LINK akzeptiert die Befehlsdatei Eingabe, als ob er an der entsprechenden Position in der Befehlszeile angegeben wurden. Befehlsdateien können nicht geschachtelt werden. LINK wiederholt den Inhalt von Befehlsdateien, es sei denn, die [/nologo](../../build/reference/nologo-suppress-startup-banner-linker.md) angegeben wird.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl zum Erstellen einer DLL übergibt die Namen von Objektdateien und Bibliotheken in separaten Befehlsdateien und verwendet eine dritte Befehlsdatei für die Angabe der Option "/ Exports":  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)