---
title: "Parametervalidierung"
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
  - "C"
helpviewer_keywords: 
  - "Parameter, Überprüfung"
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Parametervalidierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die meisten der Sicherheit\-erhöhten CRT\-Funktionen und vieler der bereits vorhandenen Funktionen überprüfen deren Parameter.  Dies kann Überprüfungszeiger für NULL, Überprüfung, dass ganze Zahlen in einem gültigen Bereich ab, oder Überprüfungen einschließen, ob Enumerationswerte gültig sind.  Wenn ein ungültiger Parameter gefunden wird, wird der ungültige Parameterhandler ausgeführt.  
  
## Ungültige Parameter\-Handler\-Routine  
 Das Verhalten der C\-Laufzeit kompiliert, wenn ein ungültiger Parameter gefunden wird, ist, die derzeit zugewiesenen ungültigen Parameterhandler aufzurufen.  Die Parameteraufrufe Watson\-Absturzberichterstellung standardmäßigen ungültige, die die Anwendung durch den Benutzer sogar abstürzt und fragt, ob er das Absturzabbild an Microsoft für die Analyse geladen werden möchten.  Im Debugmodus wird ein ungültiger Parameter auch eine Assertionsmeldung aus.  
  
 Dieses Verhalten kann geändert werden, indem die Funktion [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) verwendet, um den ungültigen Parameterhandler auf die eigene Funktion festzulegen.  Wenn die Funktion, die Sie angeben, nicht die Anwendung beendet, Steuerelement wird an die Funktion, die erhalten hat, die ungültige Parameter zurückgegeben, und diese Funktionen normalerweise überwachen Ausführung auf, geben einem Fehlercode und festgelegtem `errno` zu einem Fehlercode zurück.  In vielen Fällen sind der `errno`\-Wert und der Rückgabewert sowohl `EINVAL` und geben ein ungültiger Parameter an.  In einigen Fällen wird ein Fehlercode die spezifischen, wie `EBADF` für einen ungültigen Dateizeiger zurückgegeben, der die als Parameter übergeben wird.  Weitere Informationen über errno, finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Siehe auch  
 [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)