---
title: "Linkertoolwarnung LNK4098"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4098"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4098"
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4098
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Standardbibliothek 'Bibliothek' steht in Konflikt mit anderen Bibliotheken; \/NODEFAULTLIB:Bibliothek verwenden.  
  
 Sie versuchen, eine Verknüpfung mit nicht kompatiblen Bibliotheken herzustellen.  
  
> [!NOTE]
>  Die Laufzeitbibliotheken bieten nun Direktiven, um das Vermischen unterschiedlicher Typen zu verhindern.  Diese Warnung wird bei dem Versuch ausgegeben, unterschiedliche Typen oder Debug\- und Nicht\-Debugversionen der Laufzeitbibliothek im selben Programm zu verwenden.  Wenn Sie z. B. eine Datei zur Verwendung eines Laufzeitbibliothekstyps und eine andere Datei zur Verwendung eines anderen Typs kompiliert haben \(z. B. singlethreaded gegenüber multithreaded\) und anschließend versuchen, sie zu verknüpfen, wird diese Warnung ausgegeben.  Sie sollten alle Quelldateien für die Verwendung derselben Laufzeitbibliothek kompilieren.  Weitere Informationen finden Sie in den Compileroptionen unter [Laufzeitbibliothek verwenden](../../build/reference/md-mt-ld-use-run-time-library.md) \(**\/MD**, **\/MT**, **\/LD**\).  
  
 Sie können die Linkeroption [\/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md) verwenden, um die vom Linker gesuchten Bibliotheken zu bestimmen.  Wenn Sie LNK4098 erhalten und eine ausführbare Datei erstellen möchten, die z. B. die Singlethread\-Laufzeitbibliotheken in der Nicht\-Debugversion verwendet, stellen Sie mit der **\/VERBOSE:LIB**\-Option fest, welche Bibliotheken vom Linker gesucht werden.  Der Linker sollte **LIBC.lib** und nicht **LIBCMT.lib**, **MSVCRT.lib**, **LIBCD.lib**, **LIBCMTD.lib** oder **MSVCRTD.lib** als gesuchte Bibliotheken ausgeben.  Sie können den Linker anweisen, nicht zutreffende Laufzeitbibliotheken zu ignorieren, indem Sie [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für jede zu ignorierende Bibliothek angeben.  
  
 Aus der folgenden Tabelle ist ersichtlich, welche Bibliotheken abhängig von der gewünschten Laufzeitbibliothek ignoriert werden sollten.  
  
|Verwendete Laufzeitbibliothek|Ignorierte Bibliotheken|  
|-----------------------------------|-----------------------------|  
|Singlethreaded \(libc.lib\)|libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Multithreaded \(libcmt.lib\)|libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Multithreaded bei Verwendung von DLL \(msvcrt.lib\)|libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Singlethreaded Debugversion \(libcd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|Multithreaded Debugversion \(libcmtd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|Multithreaded Debugversion bei Verwendung von DLL \(msvcrtd.lib\)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 Wenn Sie diese Warnung erhalten haben und eine ausführbare Datei erstellen möchten, die die singlethreaded Nicht\-Debugversion der Laufzeitbibliotheken verwendet, können Sie z. B. die folgenden Optionen für den Linker verwenden:  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```