---
title: "Verwenden einer Importbibliothek und einer Exportdatei"
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
  - "Zirkuläre Exporte"
  - "Exportdateien"
  - "Importbibliotheken, Verwenden"
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden einer Importbibliothek und einer Exportdatei
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn ein Programm \(eine ausführbare Datei oder eine DLL\) in ein anderes Programm exportiert, aus dem es auch importiert, oder wenn mehr als zwei Programme gegenseitige Exporte und Importe ausführen, müssen die Befehle zum Verknüpfen dieser Programme zirkuläre Exporte zulassen.  
  
 Wenn Sie in einer Situation ohne zirkuläre Exporte ein Programm verknüpfen, welches Exporte aus einem anderen Programm verwendet, müssen Sie die Importbibliothek für das exportierende Programm angeben.  Diese Importbibliothek wird beim Verknüpfen des exportierenden Programms erstellt.  Daher müssen Sie das exportierende Programm vor dem importierenden Programm verknüpfen.  Wenn TWO.dll beispielsweise aus ONE.dll importiert, müssen Sie zuerst ONE.dll verknüpfen und die Importbibliothek ONE.lib abrufen.  Anschließend geben Sie ONE.lib beim Verknüpfen von TWO.dll an.  Wenn der Linker TWO.dll erstellt, erstellt er gleichzeitig auch ihre Importbibliothek TWO.lib.  Verwenden Sie TWO.lib beim Verknüpfen von Programmen, die aus TWO.dll importieren.  
  
 In einer zirkulären Exportsituation ist es jedoch nicht möglich, alle gegenseitig voneinander abhängigen Programme unter Verwendung der Importbibliotheken der anderen Programme zu verknüpfen.  Wenn im obigen Beispiel **ZWEI.DLL** auch in **EINS.DLL** exportiert, ist die Importbibliothek für **ZWEI.DLL** noch nicht vorhanden, wenn **EINS.DLL** verknüpft wird.  Daher müssen Sie bei derartigen zirkulären Exporten mithilfe von LIB eine Importbibliothek und eine Exportdatei für eines der Programme erstellen.  
  
 Wählen Sie zunächst das Programm aus, für das Sie LIB ausführen.  Listen Sie im LIB\-Befehl alle Objekte und Bibliotheken für das Programm auf, und geben Sie \/DEF an.  Wenn das Programm eine DEF\-Datei oder \/EXPORT\-Spezifikationen verwendet, machen Sie dieselben Angaben.  
  
 Nachdem die Importbibliothek \(**.lib**\) und die Exportdatei \(**.exp**\) für das Programm erstellt wurden, verwenden Sie die Importbibliothek, um eines oder mehrere andere Programme zu verknüpfen.  **LINK** erstellt eine Importbibliothek für jedes erstellte exportierende Programm.  Wenn Sie LIB beispielsweise für die Objekte und Exporte von ONE.dll ausführen, erstellen Sie ONE.lib und ONE.exp.  Sie können ONE.lib jetzt beim Verknüpfen von TWO.dll verwenden. Durch diesen Schritt wird außerdem die Importbibliothek TWO.lib erstellt.  
  
 Zum Schluss verknüpfen Sie Ihr Ausgangsprogramm.  Geben Sie im **LINK**\-Befehl die Objekte und Bibliotheken für das Programm, die EXP\-Datei, die von LIB für das Programm erstellt wurde, sowie die Importbibliothek\(en\) für die vom Programm verwendeten Exporte an.  Zurück zum Beispiel: Der LINK\-Befehl für ONE.dll enthält die Dateien ONE.exp und TWO.lib sowie die Objekte und Bibliotheken, die in ONE.dll enthalten sind.  Weder die DEF\-Datei noch \/EXPORT\-Spezifikationen sollten im LINK\-Befehl angegeben werden; sie werden nicht benötigt, da die Exportdefinitionen in der EXP\-Datei enthalten sind.  Wenn Sie eine Verknüpfung über eine EXP\-Datei erstellen, erstellt **LINK** keine Importbibliothek, da angenommen wird, dass diese bereits beim Erstellen der EXP\-Datei erstellt wurde.  
  
## Siehe auch  
 [Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md)