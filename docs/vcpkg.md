---
title: "vcpkg – ein C++-Paket-Manager für Windows | Microsoft-Dokumentation"
description: "Vcpkg ist ein Befehlszeilen-Paket-Manager, der den Erwerb und die Installation von Open Source-C++-Bibliotheken für Windows erheblich vereinfacht."
keywords: vcpkg
author: mikeblome
ms.author: mblome
ms.date: 05/30/2017
ms.technology: cpp-ide
ms.tgt_pltfrm: windows
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.topic: article
dev_langs: C++
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0728827cb2cd604ec4e7ff1ef58b68ed8fb64532
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vcpkg-c-package-manager-for-windows"></a>vcpkg: Ein C++-Paket-Manager für Windows 
Vcpkg ist ein Befehlszeilen-Paket-Manager, der den Erwerb und die Installation von Drittanbieterbibliotheken für Windows erheblich vereinfacht. Wenn Ihr Projekt Drittanbieterbibliotheken verwendet, wird empfohlen, dass Sie vcpkg verwenden, um diese zu installieren. Vcpkg unterstützt sowohl Open Source- als auch proprietäre Bibliotheken. Alle Bibliotheken im öffentlichen vcpkg-Katalog wurden auf ihre Kompatibilität mit Visual Studio 2015 und Visual Studio 2017 getestet. Ab Mai 2017 sind über 238 Bibliotheken im Katalog vorhanden, und die C++-Community fügt fortlaufend weitere Bibliotheken hinzu.

## <a name="simple-yet-flexible"></a>Einfach aber flexibel
Mit einem einzigen Befehl können Sie Quellen herunterladen und eine Bibliothek erstellen. Vcpkg ist selbst ein Open-Source-Projekt, das auf GitHub verfügbar ist. Sie können Ihre(n) privaten Klon(e) nach Belieben anpassen, z.B. indem Sie andere Bibliotheken oder andere Versionen von Bibliotheken als die angeben, die im öffentlichen Katalog zu finden sind. Sie können über mehrere Klone von vcpkg auf einem einzelnen Computer verfügen, wobei jeder benutzerdefinierte Sätze von Bibliotheken und/oder Kompilierungsschaltern usw. erstellt. Jeder Klon ist eine vollkommen eigenständige, x-kopierbare Umgebung mit ihrer eigenen Kopie von „vcpkg.exe“, die nur für die eigene Hierarchie verwendet wird. Vcpkg wird keinen Umgebungsvariablen hinzugefügt und verfügt über keine Abhängigkeit von der Windows-Registrierung oder Visual Studio.

## <a name="sources-not-binaries"></a>Quellen statt Binärdateien
Im Fall von Bibliotheken im öffentlichen Katalog lädt vcpkg Quellen anstelle von Binärdateien herunter[1]. Vcpkg kompiliert diese Quellen mithilfe von Visual Studio 2017 bzw. Visual Studio 2015, falls 2017 nicht installiert ist. In C++ ist es sehr wichtig, dass alle Bibliotheken, die Sie verwenden, mit dem gleichen Compiler und der gleichen Compilerversion wie der Anwendungscode kompiliert werden, der damit verknüpft ist. Durch die Verwendung von vcpkg eliminieren Sie das Potenzial für nicht übereinstimmende Binärdateien und die Probleme, die dadurch entstehen können, oder reduzieren dieses zumindest entscheidend. In Teams, in denen eine bestimmte Version des Visual C++-Compilers verwendet wird, kann ein Teammitglied vcpkg verwenden, um Quellen herunterzuladen und einen Satz von Binärdateien zu kompilieren, und anschließend den Exportbefehl verwenden, um die Binärdateien und Header für andere Teammitglieder zu zippen. Weitere Informationen finden Sie nachstehend unter „Exportieren von kompilierten Binärdateien und Headern“. 

Bei der Erstellung eines vcpkg-Klons mit privaten Bibliotheken in der Ports-Sammlung können Sie einen Port hinzufügen, der vorab erstellte Binärdateien und Header herunterlädt und eine „portfile.cmake“-Datei schreibt, die diese Dateien einfach in den gewünschten Speicherort kopiert.

[1] *Hinweis: für einige proprietäre Bibliotheken stehen Quellen nicht zur Verfügung. Vcpkg lädt in diesem Fall kompatible, vorab erstellte Binärdateien herunter.*

## <a name="installation"></a>Installation
Klonen Sie das vcpkg-Repository aus GitHub: https://github.com/Microsoft/vcpkg. Sie können es in jeden beliebigen Ordner herunterladen.

Führen Sie den Bootstrapper im Stammverzeichnis aus: bootstrap-vcpkg.bat.

## <a name="basic-tasks"></a>Grundlegende Aufgaben
  
### <a name="search-the-list-of-available-libraries"></a>Suchen nach der Liste verfügbarer Bibliotheken
Um festzustellen, welche Pakete verfügbar sind, führen Sie an der Eingabeaufforderung Folgendes aus: `vcpkg search`

Dieser Befehl zählt die Steuerelementdateien in den vcpkg-/Ports-Unterordnern auf. Es wird eine Liste wie die folgende angezeigt:

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. <https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

  Sie können nach einem Muster filtern, z.B. `vcpkg search ta`:

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library

```

### <a name="install-a-library-on-your-local-machine"></a>Installieren einer Bibliothek auf Ihrem lokalen Computer
Nachdem Sie den Namen einer Bibliothek mithilfe von `vcpkg search` erhalten, verwenden Sie `vcpkg install` zum Herunterladen der Bibliothek, und kompilieren Sie diese. Vcpkg verwendet die Portdatei der Bibliothek im Ports-Verzeichnis. Wenn keine Dreiergruppe angegeben wird, installiert und kompiliert vcpkg für die x86-Version von Windows. Wenn die Portdatei Abhängigkeiten angibt, lädt vcpkg diese ebenso herunter und installiert sie. Nach dem Herunterladen erstellt vcpkg die Bibliothek und verwendet dabei das Buildsystem, das die Bibliothek verwendet. CMake- und MSBuild-Projektdateien werden bevorzugt, jedoch wird MAKE zusammen mit jedem anderen Buildsystem unterstützt. Wenn vcpkg das angegebene Buildsystem auf dem lokalen Computer nicht finden kann, lädt es dieses herunter und installiert es.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

### <a name="list-the-libraries-already-installed"></a>Auflisten der bereits installierten Bibliotheken
Nachdem Sie einige Bibliotheken installiert haben, können Sie `vcpkg list` verwenden, um anzuzeigen, welche Sie bereits haben:

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

### <a name="integrate-with-visual-studio"></a>Integrieren in Visual Studio
#### <a name="per-user"></a>Pro Benutzer
Führen Sie `vcpkg integrate install` aus, um Visual Studio so zu konfigurieren, dass alle vcpkg-Headerdateien und -Binärdateien für jeden einzelnen Benutzer gesucht werden, ohne dass die Pfade von VC++-Verzeichnissen manuell geändert werden müssen. Wenn Sie über mehrere Klone verfügen, wird der Klon, von dem aus Sie diesen Befehl ausführen, zum neuen Standardspeicherort.

Nun können Sie auf Header einfach die #include-Anweisung ausführen, indem Sie den Ordner/Header eingeben und automatisch vervollständigen lassen. Es sind keine weiteren Schritte erforderlich, um Verknüpfungen mit Bibliotheken zu erstellen oder Projektverweise hinzuzufügen. Die folgende Abbildung zeigt, wie der Visual Studio die azure-storage-cpp-Header sucht. Vcpkg platziert seine Header im Unterordner „\installed“, partitioniert von der Zielplattform. Das folgende Diagramm zeigt die Liste der Includedateien im Unterordner `/was` für die Bibliothek:

 ![vcpkg-IntelliSense-Integration](media/vcpkg-intellisense.png "vcpkg und IntelliSense")  

#### <a name="per-project"></a>Pro Projekt
Wenn Sie eine bestimmte Version einer Bibliothek verwenden müssen, die von der Version in Ihrer aktiven vcpkg-Instanz abweicht, können Sie einen neuen Klon von vcpkg erstellen, die Portdatei für die Bibliothek bearbeiten, um die Version zu erhalten, die Sie benötigen, und dann `vcpkg install <library>` ausführen. Anschließend können Sie `vcpkg integrate project` verwenden, um ein NuGet-Paket zu erstellen, das pro Projekt auf diese Bibliothek verweist.

### <a name="export-compiled-binaries-and-headers"></a>Exportieren von kompilierten Binärdateien und Headern
Von jedem Teammitglied zu verlangen, Bibliotheken herunterzuladen und zu erstellen, kann ineffizient sein. Ein einzelnes Teammitglied kann diese Arbeit übernehmen und dann `vcpkg export` verwenden, um eine ZIP-Datei der Binärdateien und Header zu erstellen, die einfach mit anderen Teammitgliedern geteilt werden kann. 

### <a name="update-installed-libraries"></a>Aktualisieren von installierten Bibliotheken
Die öffentliche Katalog wird mit den neuesten Versionen der Bibliotheken auf dem neuesten Stand gehalten. Um zu bestimmen, welche Ihrer lokalen Bibliotheken veraltet sind, verwenden Sie `vcpkg update`. Wenn Sie bereit sind, Ihre Ports-Sammlung auf die neueste Version des Katalogs zu aktualisieren, führen Sie einfach einen Git-Pullvorgang auf das GitHub-Repository durch, oder erstellen Sie einen neuen Klon, und behalten Sie den alten, falls er noch benötigt wird.

### <a name="contribute-new-libraries"></a>Beitragen von neuen Bibliotheken
Sie können jede beliebige Bibliothek in Ihre private Ports-Sammlung aufnehmen. Um einen neue Bibliothek für den öffentlichen Katalog vorzuschlagen, öffnen Sie ein Problem auf der [GitHub-Seite zu vcpkg-Problemen](https://github.com/Microsoft/vcpkg/issues).

### <a name="remove-a-library"></a>Entfernen einer Bibliothek
Geben Sie `vcpkg remove` ein, um eine installierte Bibliothek zu entfernen. Wenn alle anderen Bibliotheken von dieser abhängen, werden Sie dazu aufgefordert, den Befehl mit `--recurse` erneut auszuführen, wodurch alle Downstreambibliotheken entfernt werden.

### <a name="customize-vcpkg"></a>Anpassen von vcpkg
Sie können Ihren Klon von vcpkg beliebig bearbeiten. Sie können mehrere vcpkg-Klone erstellen und die Portdateien in jedem bearbeiten, um bestimmte Versionen von Bibliotheken oder bestimmte Befehlszeilenparameter zu erhalten. Beispielsweise könnte in einem Unternehmen eine Gruppe von Entwicklern an einer Software arbeiten, die über einen Satz von Abhängigkeiten verfügt, und eine andere Gruppe könnte über einen anderen Satz verfügen. Sie können zwei Klone von vcpkg einrichten und jeden so bearbeiten, dass er die Bibliotheksversionen und die Kompilierungsschalter usw. entsprechend Ihren Bedürfnissen herunterlädt. 

### <a name="uninstall-vcpkg"></a>Deinstallieren von vcpkg
Löschen Sie einfach das Verzeichnis. 

## <a name="the-vcpkg-folder-hierarchy"></a>Die vcpkg-Ordnerhierarchie
Alle vcpkg-Funktionen und -Daten sind vollkommen eigenständig in einer einzigen Verzeichnishierarchie; dies nennt man eine „Instanz“. Es gibt keine Registrierungseinstellungen oder Umgebungsvariablen. Sie können über eine beliebige Anzahl von Instanzen von vcpkg auf einem Computer verfügen, ohne dass diese sich gegenseitig beeinträchtigen. 

Der Inhalt einer vcpkg-Instanz sieht folgendermaßen aus: 
- buildtrees: Enthält Unterordner von Quellen, aus denen jede Bibliothek erstellt wird.
- docs: Dokumentation und Beispiele.
- downloads: Zwischengespeicherte Kopien von heruntergeladenen Tools oder Quellen. Vcpkg sucht hier zuerst, wenn Sie den Installationsbefehl ausführen.
- installed: Enthält die Header und Binärdateien für jede installierte Bibliothek. Wenn Sie in Visual Studio integrieren, veranlassen Sie im Wesentlichen, dass dieser Ordner zu den Suchpfaden hinzugefügt wird.
- packages: Interner Ordner für das Staging zwischen Installationsvorgängen.
- ports: Dateien, die jede Bibliothek im Katalog, deren Version und den Ort beschreiben, von dem aus sie heruntergeladen werden kann. Sie können, falls nötig, Ihre eigenen Ports hinzufügen.
- scripts: Skripts (cmake, powershell), die von vcpkg verwendet werden.
- toolsrc: C++-Quellcode für vcpkg und zugehörige Komponenten.
- triplets: Enthält die Einstellung für jede unterstützte Zielplattform (z.B. x86-windows oder x64-uwp).

## <a name="command-line-reference"></a>Befehlszeilenreferenz
- vcpkg search [pat] Suchen nach zum Erstellen verfügbaren Paketen
- vcpkg install <pkg>...    Installieren eines Pakets
- vcpkg remove <pkg>...  Deinstallieren eines Pakets
- vcpkg remove --outdated Deinstallieren aller veralteten Pakete
- vcpkg list Auflisten von installierten Paketen
- vcpkg update Anzeigen einer Liste von Paketen zum Aktualisieren
- vcpkg hash <file> [alg] Berechnen des Hashwerts für eine Datei über einen bestimmten Algorithmus, Standard SHA512
- vcpkg integrate install Benutzerweites Verfügbarmachen von installierten Paketen. Erfordert Administratorrechte bei der ersten Verwendung
- vcpkg integrate remove Entfernen der benutzerweiten Integration
- vcpkg integrate project Erstellen eines Referenz-NuGet-Pakets für die individuelle VS-Projektverwendung
- vcpkg export <pkg>... [opt]...    Exportieren eines Pakets
- vcpkg edit <pkg> Öffnen eines Ports zum Bearbeiten (verwendet %EDITOR%, Standard „code“)
- vcpkg import <pkg> Importieren einer vorab erstellten Bibliothek
- vcpkg create <pkg> <url>   [archivename] Erstellen eines neuen Pakets
- vcpkg owns <pat> Suchen nach Dateien in installierten Paketen
- vcpkg cache Auflisten zwischengespeicherter kompilierter Pakete
- vcpkg version Anzeigen von Versionsinformationen
- vcpkg contact Anzeigen von Kontaktinformationen zum Senden von Feedback

### <a name="options"></a>Optionen:
  **`--triplet <t>`** Geben Sie die Zielarchitektur-Dreiergruppe an. (Standard: `%VCPKG_DEFAULT_TRIPLET%`, siehe auch `vcpkg help triplet`)

  **`--vcpkg-root <path>`** Geben Sie das vcpkg-Stammverzeichnis an (Standard: `%VCPKG_ROOT%`).
