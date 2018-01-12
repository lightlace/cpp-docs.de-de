---
title: "Manifestgenerierung über die Befehlszeile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ba88017e0003c7a552c985516dba9a6254317a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-generation-at-the-command-line"></a>Manifestgenerierung über die Befehlszeile
Beim Erstellen von C/C++-Anwendungen über die Befehlszeile mithilfe von Nmake oder ähnliche Tools, wird das Manifest generiert, nachdem der Linker verarbeitet alle Objektdateien und die endgültige Binärdatei erstellt hat. Der Linker in Objektdateien gespeicherten Assemblyinformationen erfasst und kombiniert diese Informationen in einer endgültigen Manifestdatei. Standardmäßig generiert der Linker eine Datei mit dem Namen < name_der_binärdatei >. \<Erweiterung > Manifest, um die endgültige Binärdatei zu beschreiben. Der Linker bettet die Manifestdatei in die Binärdatei nicht und kann nur ein Manifest als externe Datei generieren. Es gibt mehrere Möglichkeiten zum Einbetten eines Manifests in die endgültige Binärdatei, z. B. mit der [Manifesttool (mt.exe)](http://msdn.microsoft.com/library/aa375649) oder Kompilieren das Manifest in eine Ressourcendatei. Es ist wichtig zu bedenken, die bestimmte Regeln befolgt werden, wenn das Einbetten eines Manifests in die endgültige Binärdatei mit Funktionen wie inkrementelles Verknüpfen aktivieren "Signierung", und bearbeiten und fortfahren. Diese und andere Optionen werden im erläutert [Vorgehensweise: Einbetten einer Manifest innerhalb eines C/C++-Anwendung](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) beim Erstellen über die Befehlszeile.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsmanifeste](http://msdn.microsoft.com/library/aa375365)   
 [/ INCREMENTAL (inkrementell verknüpfen)](../build/reference/incremental-link-incrementally.md)   
 [Assemblys mit starken Namen (Assemblysignierung) (C + c++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [Bearbeiten und fortfahren](/visualstudio/debugger/edit-and-continue)   
 [Manifestgenerierung für C/C++-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)