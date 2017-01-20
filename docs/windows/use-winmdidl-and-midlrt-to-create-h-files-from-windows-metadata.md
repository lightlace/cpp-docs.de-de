---
title: "Gewusst wie: Verwenden von winmdidl.exe und midlrt.exe zum Erstellen von .h-Dateien aus Windows-Metadaten"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von winmdidl.exe und midlrt.exe zum Erstellen von .h-Dateien aus Windows-Metadaten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"Winmdidl.exe" und "midlrt.exe" aktivieren Interaktionen auf COM\-Ebene zwischen systemeigenem C\+\+\-Code und Komponenten für Windows\-Runtime.  "Winmdidl.exe" verwendet als Eingabe eine WINMD\-Datei, die Metadaten für eine Komponente für Windows\-Runtime enthält, und gibt eine IDL\-Datei aus.  "Midlrt.exe" konvertiert diese IDL\-Datei in Headerdateien, die der C\+\+\-Code verarbeiten kann.  Beide Tools werden an der Befehlszeile ausgeführt.  
  
 Sie verwenden diese Tools in zwei Hauptszenarien:  
  
-   Erstellen von benutzerdefinierten IDL\-Dateien und Headerdateien, sodass eine C\+\+\-App, die mithilfe der Vorlagenbibliothek für Windows\-Runtime geschrieben wurde, eine benutzerdefinierte Komponente für Windows\-Runtime verarbeiten kann  
  
-   Generieren von Proxy\- und Stub\-Dateien für benutzerdefinierte Ereignistypen in einer Komponente für Windows\-Runtime  Weitere Informationen finden Sie unter [Auslösen von Ereignissen in Windows\-Runtime\-Komponenten](../Topic/Raising%20Events%20in%20Windows%20Runtime%20Components.md).  
  
 Diese Tools sind nur für das Analysieren von benutzerdefinierten WINMD\-Dateien erforderlich.  Die IDL\- und H\-Dateien für Komponenten des Windows\-Betriebssystems sind bereits für Sie generiert.  In [!INCLUDE[win81](../misc/includes/win81_md.md)] befinden sie sich standardmäßig unter "\\Programme \(x86\)\\Windows Kits\\8.1\\Include\\winrt\\".  
  
## Speicherort der Tools  
 In [!INCLUDE[win81](../misc/includes/win81_md.md)] befinden sich "winmdidl.exe" und "midlrt.exe" standardmäßig unter "C:\\Programme \(x86\)\\Windows Kits\\8.1\\".  Versionen der Tools sind auch in den Ordnern "\\bin\\x86\\" und "\\bin\\x64\\" verfügbar.  
  
## Winmdidl\-Befehlszeilenargumente  
  
```  
  
Winmdidl.exe [/nologo] [/supressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile  
  
```  
  
 `/nologo`  
 Verhindert die Anzeige der winmdidl\-Copyrightmeldung und \-Versionsnummer auf der Konsole.  
  
 `/supressversioncheck`  
 Nicht verwendet.  
  
 `/time`  
 Zeigt die gesamte Ausführungszeit in der Konsolenausgabe an.  
  
 \/outdir:\<dir\>  
 Gibt ein Ausgabeverzeichnis an.  Wenn der Pfad Leerzeichen enthält, verwenden Sie Anführungszeichen.  Das Standardausgabeverzeichnis ist „*\<Laufwerk\>*:\\Users\\*\<Benutzername\>*\\AppData\\Local\\VirtualStore\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\“.  
  
 `/banner:<file>`  
 Gibt eine Datei an, die benutzerdefinierten Text enthält, der am Anfang der generierten IDL\-Datei der standardmäßigen Copyrightmeldung und winmdidl\-Versionsnummer vorangestellt wird.  Wenn der Pfad Leerzeichen enthält, verwenden Sie Anführungszeichen.  
  
 `/utf8`  
 Bewirkt, dass die Datei als UTF\-8 formatiert wird.  
  
 `Winmdfile`  
 Der Dateiname der zu analysierenden WINMD\-Datei.  Wenn der Pfad Leerzeichen enthält, verwenden Sie Anführungszeichen.  
  
## Midlrt\-Befehlszeilenargumente  
 Siehe [Seite zu MIDLRT und Komponenten für Windows\-Runtime](http://msdn.microsoft.com/library/windows/desktop/hh869900\(v=vs.85\).aspx).  
  
## Beispiele  
 Das folgende Beispiel zeigt einen winmdidl\-Befehl an einer Visual Studio\-x86\-Eingabeaufforderung.  Es wird ein Ausgabeverzeichnis und eine Datei angegeben, die speziellen Bannertext enthält, der der generierten IDL\-Datei hinzugefügt wird.  
  
 **C:\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\>winmdidl \/nologo \/outdir:c:\\users\\giraffe\\documents\\ \/banner:c:\\users\\giraffe\\documents\\banner.txt "C:\\Users\\giraffe\\Documents\\Visual Studio 2013\\Projects\\Test\_for\_winmdidl\\Debug\\Test\_for\_winmdidl\\test\_for\_winmdidl.winmd"**  
  
 Im folgenden Beispiel wird die Konsolenanzeige von "winmdidl" gezeigt, die angibt, dass der Vorgang erfolgreich war.  
  
 **Generating c:\\users\\giraffe\\documents\\\\Test\_for\_winmdidl.idl**  
  
 Anschließend wird "midlrt" auf der generierten IDL\-Datei ausgeführt.  Beachten Sie, dass das **metadata\_dir**\-Argument nach dem Namen der IDL\-Datei angegeben wird.  Der Pfad von "\\WinMetadata\\" ist erforderlich – es ist der Speicherort für "windows.winmd".  
  
 **C:\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\> midlrt "c:\\users\\mblome\\documents\\test\_for\_winmdidl.idl" \/metadata\_dir "C:\\Windows\\System32\\WinMetadata"**  
  
## Hinweise  
 Die Ausgabedatei eines winmdidl\-Vorgangs weist denselben Namen wie die Eingabedatei auf, hat aber die Dateinamenerweiterung IDL.  
  
 Wenn Sie eine Komponente für Windows\-Runtime entwickeln, auf die von WRL zugegriffen wird, können Sie "winmdidl.exe" und "midlrt.exe" angeben, um als Postbuildschritte ausgeführt zu werden, sodass die IDL\- und H\-Dateien für jedes Build erzeugt werden.  Ein Beispiel finden Sie unter [Auslösen von Ereignissen in Windows\-Runtime\-Komponenten](../Topic/Raising%20Events%20in%20Windows%20Runtime%20Components.md).