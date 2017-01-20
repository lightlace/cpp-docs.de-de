---
title: "R&#252;ckgabewert von cl.exe"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Rückgabewert"
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# R&#252;ckgabewert von cl.exe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe gibt 0 \(null\) für Erfolg \(keine Fehler\) und andernfalls einen Wert ungleich 0 \(null\) zurück.  
  
 Der Rückgabewert von cl.exe kann nützlich sein, wenn Sie mit einer Skript\-, PowerShell\-, CMD\- oder BAT\-Datei kompilieren.  Es wird empfohlen, die Ausgabe des Compilers aufzuzeichnen, um mögliche Fehler oder Warnmeldungen beheben zu können.  
  
 Es gibt weitaus mehr mögliche Exitcodes bei Fehlern, als cl.exe auflisten könnte.  Sie können den Fehlercode in den Dateien "winerror.h" oder "ntstatus.h" nachschlagen, die im Windows Software Development Kit im Verzeichnis %Programme\(x86\)%\\Windows Kits\\`version`\\Include\\shared\\ enthalten sind.  Im Dezimalformat zurückgegebene Fehlercodes müssen für die Suche in das Hexadezimalformat konvertiert werden.  Beispiel: Der Fehlercode \-1073741620 entspricht im Hexadezimalformat 0xC00000CC.  Dieser Fehler befindet sich in der Datei "ntstatus.h" mit der entsprechenden Meldung "Der angegebene Freigabename wurde auf dem Server nicht gefunden". Eine herunterladbare Liste der Windows\-Fehlercodes finden Sie unter [&#91;MS\-ERREF&#93;: Windows Error Codes](assetId:///1bc92ddf-b79e-413c-bbaa-99a5281a6c90).  
  
 Sie können die Bedeutung einer Fehlermeldung des Compilers auch mit dem Hilfsprogramm für die Fehlersuche von Visual Studio herausfinden.  Geben Sie hierzu in einer Visual Studio\-Befehlsshell **errlook.exe** ein, um das Hilfsprogramm zu starten. Alternativ können Sie in der Menüleiste der Visual Studio IDE die Option **Extras**, **Fehlersuche** auswählen.  Geben Sie den Fehlerwert ein, um den beschreibenden Text zu finden, der mit dem Fehler verknüpft ist.  Weitere Informationen finden Sie unter [ERRLOOK\-Referenz](../../build/reference/errlook-reference.md).  
  
## Hinweise  
 Bei dem folgenden Beispiel handelt es sich um eine BAT\-Datei, die den Rückgabewert von cl.exe verwendet.  
  
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
  
## Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)