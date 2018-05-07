---
title: XDCMake-Verweis | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xdcmake-reference"></a>XDCMake-Verweis
XDCMake.exe ist ein Programm, das XDC-Dateien in eine XML-Datei kompiliert wird. Eine XDC-Datei wird vom Visual C++-Compiler für jede Quelldatei erstellt, beim Kompilieren von Quellcode mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) und wenn die Quellcodedatei enthält Dokumentationskommentare mit XML-Tags markiert.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Verwenden von xdcmake.exe in der Visual Studio-Entwicklungsumgebung  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
2.  Öffnen der **Konfigurationseigenschaften** Ordner.  
  
3.  Klicken Sie auf die **XML-Dokumentkommentare** Eigenschaftenseite.  
  
> [!NOTE]
>  XDCMake.exe-Optionen in der Befehlszeile unterscheiden sich von den Optionen, wenn xdcmake.exe in der Entwicklungsumgebung (Eigenschaftenseiten) verwendet wird. Informationen zum Verwenden von xdcmake.exe in der Entwicklungsumgebung finden Sie unter [Eigenschaftenseiten für das XML-Dokument-Generator-Tool](../ide/xml-document-generator-tool-property-pages.md).  
  
## <a name="syntax"></a>Syntax  
 XDCMake `input_filename options`  
  
## <a name="parameters"></a>Parameter  
 Dabei gilt:  
  
 `input_filename`  
 Der Dateiname der XDC-Dateien als Eingabe für xdcmake.exe verwendet werden soll. Geben Sie eine oder mehrere XDC-Dateien, oder verwenden Sie *.XDC, um alle XDC-Dateien im aktuellen Verzeichnis zu verwenden.  
  
 `options`  
 0 (null) oder mehrere der folgenden:  
  
|Option|Beschreibung|  
|------------|-----------------|  
|/?, / help|Zeigt die Hilfe für xdcmake.exe.|  
|/ Assembly:*Dateiname*|Ermöglicht die Angabe den Wert von der \<Assembly >-Tag in der XML-Datei.  Wird standardmäßig der Wert von der \<Assembly >-Tag ist identisch mit den Dateinamen der XML-Datei.|  
|/nologo|Unterdrückt die Copyrightmeldung.|  
|/ out:*Dateiname*|Sie können den Namen der XML-Datei angeben.  Standardmäßig ist der Name der XML-Datei den Dateinamen des ersten XDC-Datei, die von xdcmake.exe verarbeitet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Studio wird xdcmake.exe automatisch aufgerufen, wenn Sie ein Projekt erstellen. Sie können auch xdcmake.exe in der Befehlszeile aufrufen.  
  
 Finden Sie unter [empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) für Weitere Informationen zum Hinzufügen von Dokumentationskommentaren zu Quellcodedateien.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)