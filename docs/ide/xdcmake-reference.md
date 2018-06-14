---
title: XDCMake-Referenz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383347dc5cd1ce0dcadff6bdee802b90fd52e85d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333904"
---
# <a name="xdcmake-reference"></a>XDCMake-Verweis
„xdcmake.exe“ ist ein Programm, das XDC-Dateien in eine XML-Datei-kompiliert. Der Visual C++-Compiler erstellt eine XDC-Datei für jede Quellcodedatei, wenn der Quellcode mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert wird und die Quellcodedatei Dokumentationskommentare enthält, die mit XML-Tags hervorgehoben werden.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>So verwenden Sie die „xdcmake.exe“ in der Visual Studio-Entwicklungsumgebung  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).  
  
2.  Öffnen Sie den Ordner **Konfigurationseigenschaften**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **XML-Dokumentationskommentare**.  
  
> [!NOTE]
>  Die Optionen von „xdcmake.exe“ in der Befehlszeile unterscheiden sich von den Optionen, wenn „xdcmake.exe“ in der Entwicklungsumgebung (Eigenschaftenseiten) verwendet wird. Informationen über die Verwendung von „xdcmake.exe“ in der Entwicklungsumgebung finden Sie unter [XML Document Generator Tool Property Pages (Eigenschaftenseiten für das Tool XML-Dokument-Generator)](../ide/xml-document-generator-tool-property-pages.md).  
  
## <a name="syntax"></a>Syntax  
 xdcmake `input_filename options`  
  
## <a name="parameters"></a>Parameter  
 Dabei gilt:  
  
 `input_filename`  
 Der Dateiname der XDC-Dateien wird als Eingabe für „xdcmake.exe“ verwendet. Geben Sie mindestens eine XDC-Datei an, oder verwenden Sie „*.xdc“, um alle XDC-Dateien im aktuellen Verzeichnis zu verwenden.  
  
 `options`  
 0 (null) oder mehrere der Folgenden:  
  
|Option|Beschreibung|  
|------------|-----------------|  
|/?, /help|Zeigt Hilfe für die Datei „xdcmake.exe“ an.|  
|/assembly:*Dateiname*|Ermöglicht die Angabe des Werts des \<assembly>-Tags in der XML-Datei.  Der Wert des \<assembly>-Tags ist standardmäßig identisch mit dem Dateinamen der XML-Datei.|  
|/nologo|Copyrightmeldung unterdrücken|  
|/out:*Dateiname*|Ermöglicht die Angabe des Namens der XML-Datei.  Der Name der XML-Datei ist standardmäßig der Dateiname der ersten XDC-Datei, die von der „xdcmake.exe“ verarbeitet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Studio ruft „xdcmake.exe“ automatisch auf, wenn ein Projekt erstellt wird. Sie können „xdcmake.exe“ auch von der Befehlszeile aus aufrufen.  
  
 Weitere Informationen zum Hinzufügen von Dokumentationskommentaren in Quellcodedateien finden Sie unter [Recommended Tags for Documentation Comments (Empfohlene Tags für Dokumentationskommentare)](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)