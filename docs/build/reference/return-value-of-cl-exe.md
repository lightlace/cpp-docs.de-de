---
title: "Rückgabewert von cl.exe | Microsoft Docs"
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
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85ca64178a4914cfbbc8b3a717b87ab5590cd778
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="return-value-of-clexe"></a>Rückgabewert von cl.exe
cl.exe gibt 0 (null) für Erfolg (keine Fehler) und andernfalls einen Wert ungleich 0 (null) zurück.  
  
 Der Rückgabewert von cl.exe kann nützlich sein, wenn Sie mit einer Skript-, PowerShell-, CMD- oder BAT-Datei kompilieren. Es wird empfohlen, die Ausgabe des Compilers aufzuzeichnen, um mögliche Fehler oder Warnmeldungen beheben zu können.  
  
 Es gibt weitaus mehr mögliche Exitcodes bei Fehlern, als cl.exe auflisten könnte. Sie können den Fehlercode in der Datei "Winerror.h" Nachschlagen oder die Datei "NTSTATUS.h" Dateien in das Windows Software Development Kit % ProgramFiles% (x86) %\Windows Kits enthalten\\`version`\Include\shared\-Verzeichnis. Im Dezimalformat zurückgegebene Fehlercodes müssen für die Suche in das Hexadezimalformat konvertiert werden. Beispiel: Der Fehlercode -1073741620 entspricht im Hexadezimalformat 0xC00000CC. Dieser Fehler befindet sich in der Datei "ntstatus.h" mit der entsprechenden Meldung "Der angegebene Freigabename wurde auf dem Server nicht gefunden". Eine herunterladbare Liste der Windows-Fehlercodes finden Sie [&#91; MS-ERREF &#93;: Windows-Fehlercodes](http://msdn.microsoft.com/library/cc231196).  
  
 Sie können die Bedeutung einer Fehlermeldung des Compilers auch mit dem Hilfsprogramm für die Fehlersuche von Visual Studio herausfinden. Geben Sie in einer Visual Studio-Befehlsshell **errlook.exe** , starten Sie das Dienstprogramm; oder wählen in der Visual Studio-IDE, in der Menüleiste **Tools**, **Fehlersuche**. Geben Sie den Fehlerwert ein, um den beschreibenden Text zu finden, der mit dem Fehler verknüpft ist. Weitere Informationen finden Sie unter [ERRLOOK-Referenz](../../build/reference/errlook-reference.md).  
  
## <a name="remarks"></a>Hinweise  
 Bei dem folgenden Beispiel handelt es sich um eine BAT-Datei, die den Rückgabewert von cl.exe verwendet.  
  
```  
echo off  
cl /W4 t.cpp  
@if ERRORLEVEL == 0 (  
   goto good  
)  
  
@if ERRORLEVEL != 0 (  
   goto bad  
)  
  
:good  
   echo "clean compile"  
   echo %ERRORLEVEL%  
   goto end  
  
:bad  
   echo "error or warning"  
   echo %ERRORLEVEL%  
   goto end  
  
:end  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)