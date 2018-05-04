---
title: -PDBALTPATH (mit alternativen PDB-Pfad) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbaltpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dec06c3d6a8a981a059f173700e716431acc53a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Use Alternate PDB Path)
```  
/PDBALTPATH:pdb_file_name  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *pdb_file_name*  
 Der Pfad und der Dateiname für die .pdb-Datei.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um einen alternativen Speicherort für die Programmdatenbankdatei (.pdb) in einer kompilierten Binärdatei bereitzustellen. Normalerweise zeichnet der Linker den Speicherort der .pdb-Dateien in den Binärdateien auf, die er produziert. Sie können diese Option verwenden, um einen anderen Pfad und Dateinamen für die .pdb-Datei bereitzustellen. Die mit /PDBALTPATH bereitgestellten Informationen ändern weder den Standort noch den Namen der tatsächlichen .pdb-Datei, sondern sie ändern die Informationen, die der Linker in die Binärdatei schreibt. Damit können Sie einen Pfad bereitstellen, der unabhängig von der Dateistruktur des Buildcomputers ist. Zwei typische Verwendungszwecke für die Option ist die Bereitstellung eines Netzwerkpfads oder einer Datei, die keine Pfadinformationen hat.  
  
 Der Wert der *Pdb_file_name* kann eine beliebige Zeichenfolge, eine Umgebungsvariable oder **%_PDB%**. Der Linker erweitert eine Umgebungsvariable wie z. B. **"% SystemRoot%"**, auf den Wert. Der Linker definiert die Umgebungsvariablen **%_PDB%** und **%_EXT%**. **%_PDB%** auf den Dateinamen der tatsächlichen .pdb-Datei ohne Pfadinformationen erweitert und **%_EXT%** ist die Erweiterung der generierten ausführbaren Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)   
 [/PDBPATH](../../build/reference/pdbpath.md)