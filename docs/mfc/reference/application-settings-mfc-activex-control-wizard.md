---
title: Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ad19a4c9726378a54bd68173decd2469c17ec75
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708566"
---
# <a name="application-settings-mfc-activex-control-wizard"></a>Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent
Verwenden Sie diese Seite des MFC-ActiveX-Steuerelement-Assistenten, um grundlegende Features zu entwerfen und zu einem neuen MFC-ActiveX-Projekt hinzuzufügen. Diese Einstellungen gelten für die Anwendung selbst und nicht für ein bestimmtes Feature oder ein Element des Steuerelements.  
  
- **Laufzeitlizenz**

   Wählen Sie diese Option aus, um eine Benutzerlizenzdatei zu generieren, die mit dem Steuerelement verteilt wird. Die Lizenz ist eine Textdatei, „ *projname*.lic“. Diese Datei muss sich in demselben Verzeichnis wie die DLL des Steuerelements befinden, damit eine Instanz des Steuerelements in einer Entwurfszeitumgebung erstellt werden kann. Normalerweise verteilen Sie diese Datei mit dem Steuerelement, aber sie wird nicht von Ihren Kunden weiterverteilt.  
  
- **Hilfedateien generieren**

   Wählen Sie diese Option aus, um Hilfedateien zu generieren, für die ein Stub ausgeführt wurde, und das Projekt zu konfigurieren, um die Hilfe für das Steuerelement einzubeziehen. Ein ohne diese Option erstelltes Standardprojekt generiert nur ein **Info** -Feld, das angezeigt wird, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt, F1 verwendet oder im Container des Steuerelements auf **Hilfe** (?) klickt.  
  
   > [!NOTE]
   > Wie die Hilfe angezeigt wird, hängt von der Interaktion zwischen Steuerelement und Container ab. Wenn Sie die Hilfe in den Container einbeziehen, müssen Sie die Nachrichten zwischen Steuerelement und Container verarbeiten, um die Hilfe entsprechend anzuzeigen.  
  
   Wenn Sie Hilfedateien mithilfe des Assistenten generieren, umfasst Ihr Projekt Folgendes:  
  
   - Die VCXPROJ-Datei enthält Code zum Erstellen und Konfigurieren der Hilfedatei, wenn das Projekt erstellt wird.  
  
   - Die Datei *ProjnamePropPage*cpp-Datei enthält eine [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo) -Funktion im Konstruktor.  
  
   - Die Datei „projname.hpj“ ist die Hilfeprojektdatei, die vom Hilfecompiler zum Erstellen der Hilfedatei des ActiveX-Steuerelements verwendet wird. Die HPJ-Datei ist eine Textdatei mit Informationen zur Erstellung der Hilfedatei sowie der Pfade zu den zusätzlichen Dateien (z. B. Bitmaps), die die Hilfedatei enthält.  
  
   - Das Projekt enthält das HLP-Verzeichnis, das die Bitmapdateien der Projekthilfe und die Hilfethemendatei (*Projektname*.rtf) enthalten soll. Diese Hilfethemendatei enthält die Standardhilfethemen für die allgemeinen Eigenschaften, Ereignisse und Methoden, die von vielen ActiveX-Steuerelementen unterstützt werden. Sie können die RTF-Datei bearbeiten, um bestimmte Hilfethemen hinzuzufügen oder zu entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Steuerelementnamen Sie, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-names-mfc-activex-control-wizard.md)   
 [Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)

