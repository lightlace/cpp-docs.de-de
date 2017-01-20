---
title: "Bereitstellung in Visual&#160;C++"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Anwendungsbereitstellung [C++]"
  - "Bereitstellen von Anwendungen [C++]"
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# Bereitstellung in Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Anwendung auf einem anderen Computer bereitgestellt werden soll, müssen sowohl die Anwendung selbst sowie alle Bibliotheksdateien installiert werden, von denen sie abhängt.  Wenn eine Bibliothek aktualisiert wird – beispielsweise wenn ein Sicherheitsrisiko behoben wird – möchten Sie möglicherweise die Aktualisierung überall anwenden, wo Ihre Anwendung bereitgestellt wird.  
  
 Visual Studio bietet drei Möglichkeiten, die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken zusammen mit Ihrer Anwendung bereitzustellen: zentrale Bereitstellung, lokale Bereitstellung und statische Verknüpfung.  Microsoft aktualisiert die zentral bereitgestellten Bibliotheken automatisch.  Für [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken, die lokal bereitgestellt oder statisch verknüpft sind, muss der Anwendungs\-Writer die Updates bereitstellen.  
  
## Zentrale Bereitstellung  
 Bei der zentralen Bereitstellung werden [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheksdateien im Verzeichnis %windir%\\system32\\ installiert.  Sie können [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken mithilfe eines der folgenden Elemente zentral bereitstellen:  
  
-   *Weiter verteilbare Paketdateien*, die eigenständige ausführbare Befehlszeilendateien sind, mit denen Sie die weiter verteilbaren [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken installieren können.  
  
-   *Weiter verteilbare Mergemodule \(MSM\-Dateien\)*, mit denen Sie bestimmte Bibliotheken bereitstellen können und die Sie in die Windows Installer\-\(MSI\)\-Datei der Anwendung einschließen können.  
  
 Eine weiter verteilbare Paketdatei installiert die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken für eine bestimmte Systemarchitektur.  Sie können das Setup Ihrer Anwendung so programmieren, dass es als erforderliche Komponente ausgeführt wird, bevor Sie die Anwendung installieren.  Ein Mergemodul aktiviert die Einbeziehung einer Setuplogik für eine bestimmte [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliothek in einer Anwendungssetupdatei von Windows Installer.  Sie können so viele Mergemodule einschließen, wie Sie für die Anwendung benötigen.  
  
 Da durch die zentrale Bereitstellung von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken mithilfe eines weiter verteilbaren Pakets die automatische Aktualisierung durch Microsoft aktiviert wird, empfehlen wir, dass Sie dynamisches Verknüpfen und weiter verteilbare Pakete für Ihre Anwendung verwenden.  
  
## Lokale Bereitstellung  
 Bei der lokalen Bereitstellung werden Bibliotheksdateien im Anwendungsordner zusammen mit der ausführbaren Datei installiert.  Verschiedene Bibliotheksversionen können im selben Ordner installiert werden, da der Dateiname jeder Version durch das Einfügen ihrer Versionsnummer eindeutig bezeichnet wird.  Version 12 der C\-Laufzeit ist beispielsweise msvcr120.dll.  
  
 Da Microsoft lokal bereitgestellte [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken nicht automatisch aktualisieren kann, raten wir von der lokalen Bereitstellung dieser Bibliotheken ab.  Wenn Sie sich für die lokale Bereitstellung von weiter verteilbaren Bibliotheken entscheiden, wird empfohlen, dass Sie eine eigene Methode zur automatischen Aktualisierung von lokal bereitgestellten Bibliotheken implementieren.  
  
## Statische Verknüpfung  
 Sie können eine [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliothek statisch mit einer Anwendung verknüpfen – das heißt, sie in die Anwendung zu kompilieren – sodass Sie die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliothekdateien nicht separat bereitstellen müssen.  Von dieser Vorgehensweise wird jedoch abgeraten, da statisch verknüpfte Bibliotheken nicht an Ort und Stelle aktualisiert werden können.  Wenn Sie statische Verknüpfung verwenden und eine verknüpfte Bibliothek aktualisieren möchten, müssen Sie die Anwendung erneut kompilieren und erneut bereitstellen.  
  
## Problembehandlung  
 Die Ladereihenfolge von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Bibliotheken hängt vom System ab.  Verwenden Sie "depends.exe" oder "where.exe", um Ladeprogrammprobleme zu diagnostizieren.  Weitere Informationen finden Sie unter [Dynamic\-Link Library Search Order \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).  
  
## Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)