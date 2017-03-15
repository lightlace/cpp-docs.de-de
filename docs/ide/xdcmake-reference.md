---
title: "XDCMake-Verweis | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xdcmake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "xdcmake (Programm)"
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# XDCMake-Verweis
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

xdcmake.exe ist ein Programm, das .xdc\-Dateien in eine XML\-Datei kompiliert.  Eine XDC\-Datei wird vom Visual C\+\+\-Compiler für jede Quellcodedatei erstellt, wenn Quellcode mit [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert wird und wenn die Quellcodedatei die Dokumentationskommentare enthält, die oben mit XML\-Tags gekennzeichnet werden.  
  
### So xdcmake.exe in der Visual Studio\-Entwicklungsumgebung verwenden  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md).  
  
2.  Öffnen Sie den Ordner **Konfigurationseigenschaften**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **XML\-Dokument\-Kommentare**.  
  
> [!NOTE]
>  xdcmake.exe\-Optionen an der Befehlszeile unterscheiden sich von den Optionen, wenn xdcmake.exe in der Entwicklungsumgebung \(Eigenschaftenseiten\) verwendet wird.  Weitere Informationen zur Verwendung von xdcmake.exe in der Entwicklungsumgebung, finden Sie unter [Eigenschaftenseiten für das Tool XML\-Dokument\-Generator](../ide/xml-document-generator-tool-property-pages.md).  
  
## Syntax  
 xdcmake `input_filename options`  
  
## Parameter  
 Dabei gilt:  
  
 `input_filename`  
 Der Dateiname der .xdc\-Dateien verwendet als Eingabe zu xdcmake.exe.  Geben Sie eine oder mehrere .xdc\-Dateien an oder verwenden Sie \*.xdc, um alle .xdc\-Dateien im aktuellen Verzeichnis zu verwenden.  
  
 `options`  
 Beliebige aus:  
  
|Option|Beschreibung|  
|------------|------------------|  
|\/?, \/help|Zeigt die Hilfe an für xdcmake.exe.|  
|\/assembly:*Dateiname*|Hier können Sie den Wert des \<assembly\>\-Tags in der XML\-Datei angeben.  Standardmäßig ist der Wert des \<assembly\>\-Tags der gleiche wie der Dateiname der XML\-Datei.|  
|\/nologo|Unterdrückt die Copyrightmeldung.|  
|\/out:*Dateiname*|Hier können Sie den Namen der XML\-Datei angeben.  Standardmäßig ist der Name der XML\-Datei der Dateiname der ersten XDC\-Datei, die von xdcmake.exe verarbeitet wird.|  
  
## Hinweise  
 Visual Studio ruft xdcmake.exe automatisch auf, wenn ein Projekt erstellt.  Sie können xdcmake.exe an der Befehlszeile auch aufrufen.  
  
 Siehe [Empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) zu Informationen über das Hinzufügen von Dokumentationskommentaren auf Quellcodedateien.  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)