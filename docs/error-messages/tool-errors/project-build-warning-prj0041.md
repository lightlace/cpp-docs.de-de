---
title: Projektbuildwarnung prj0041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e845967b0a7116d6edade98b571de5bc1bcd9a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318060"
---
# <a name="project-build-warning-prj0041"></a>Projektbuildwarnung PRJ0041
Kann nicht gefunden werden fehlende Abhängigkeit 'Abhängigkeit' für Datei "File". Das Projekt kann zwar erstellt, aber unter Umständen nicht mehr aktuell angezeigt werden, bis diese Datei gefunden wird.  
  
 Eine Datei (Ressourcendatei oder.idl/.odl-Datei, z. B. enthalten eine Include-Anweisung, die das Projektsystem nicht aufgelöst werden konnte.  
  
 Da das Projektsystem präprozessoranweisungen (z. B. #if) nicht verarbeitet werden, möglicherweise die problematische Anweisung nicht tatsächlich Teil des Builds.  
  
 Um diese Warnung zu beheben, löschen Sie alle nicht benötigten Code in der RC-Dateien oder fügen Sie Platzhalterdateien mit dem entsprechenden Namen hinzu.