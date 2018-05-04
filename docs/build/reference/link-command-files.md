---
title: LINK-Befehlsdateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6614af87f072c54353ead39c2c5ca789da18dbb8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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