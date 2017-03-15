---
title: ATL-Projekt Standardkonfigurationen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, default configurations
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 41ab65c411bef478d063e5165d3167f58ace37d7
ms.lasthandoff: 02/24/2017

---
# <a name="default-atl-project-configurations"></a>Standardmäßige ATL-Projektkonfigurationen
In diesem Thema werden die standardmäßigen Projektkonfigurationen in Visual C++ .NET mit der standardmäßigen Projektkonfigurationen in Visual C++ 6.0 verglichen.  
  
## <a name="visual-c-net-default-configurations"></a>Visual C++ .NET Standardkonfigurationen  
 Zwei Konfigurationen von ATL-Projekt-Assistenten in Visual C++ .NET wird standardmäßig erstellt.  
  
### <a name="visual-c-net-configurations"></a>Visual C++ .NET Konfigurationen  
  
|Konfiguration|Zeichensatz|Verwendung von ATL|  
|-------------------|-------------------|----------------|  
|Version|MBCS|DLL|  
|Debuggen|MBCS|DLL|  
  
 **Zeichensatz**, **Verwendung von ATL** und alle in geändert werden können die **Projekteinstellungen** Dialogfeld unter der **allgemeine** Registerkarte. Sie können auch eigene Konfigurationen mithilfe des Konfigurations-Managers hinzufügen. Weitere Informationen finden Sie unter [Buildkonfigurationen](/visualstudio/ide/understanding-build-configurations).  
  
## <a name="version-60-default-configurations"></a>Version 6.0 von Standardkonfigurationen  
 In Visual C++, Version 6.0 erstellt der ATL-COM-AppWizard (jetzt die ATL-Projekt-Assistent genannt) sechs Projektkonfigurationen standardmäßig. Die Konfigurationen sind Variationen von Version, Debuggen, Unicode und Verwenden der CRT und ATL-Einstellungen. All diese Konfigurationen können in Visual C++ .NET mit dem Konfigurations-Manager dupliziert werden, bei Bedarf.  
  
### <a name="version-60-configurations"></a>Version 6.0-Konfigurationen  
  
|Konfiguration|Zeichensatz|Verwendung von ATL|  
|-------------------|-------------------|----------------|  
|Debuggen|MBCS|Statisch|  
|Debuggen von Unicode|UNICODE|Statisch|  
|Version Min Abhängigkeit|MBCS|Statisch|  
|Version Min Abhängigkeit Unicode|UNICODE|Statisch|  
|Version Min. Größe|MBCS|DLL|  
|Version Min. Größe Unicode|UNICODE|DLL|  
  
## <a name="see-also"></a>Siehe auch  
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)   
 [Configuration Manager (Dialogfeld)](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Kompilieren und Erstellen](/visualstudio/ide/compiling-and-building-in-visual-studio)


