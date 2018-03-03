---
title: "Projektvorlage für WRL-Klassenbibliothek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13fc476f696bdd2cb17ed58c496c63747db90322
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wrl-class-library-project-template"></a>Projektvorlage für WRL-Klassenbibliothek
Wenn Sie Visual Studio verwenden, um ein Projekt für die Windows Runtime C++ Template Library (WRL) zu schreiben, können Sie Ihre Aufgabe erheblich vereinfachen, durch die WRL-klassenbibliotheksprojektvorlage herunterladen.  
  
> [!NOTE]
>  Wenn Sie die projekteinstellungen für ein vorhandenes Projekt manuell aktualisieren müssen, finden Sie unter [DLLs (C + c++ / CX)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## <a name="download-the-wrl-project-template"></a>Herunterladen der Projektvorlage für WRL  
 Visual Studio stellt keine Vorlage für Windows Runtime C++ Template Library-Projekte bereit. Hier wird erklärt, wie eine Projektvorlage herunterladen, die eine einfache Klassenbibliothek für universelle Windows-Plattform-apps mit Windows Runtime C++ Template Library erstellt.  
  
#### <a name="to-download-the-wrl-project-template"></a>Die Projektvorlage für WRL herunterladen  
  
1.  Wählen Sie in der Menüleiste **Datei**, **neues Projekt**.  
  
2.  Im linken Bereich des der **neues Projekt** wählen Sie im Dialogfeld **Online**, und wählen Sie dann **Vorlagen**.  
  
3.  In der **Onlinevorlagen suchen** Feld in der oberen rechten Ecke Typ `WRL Class Library`. Wenn die Vorlage in den Suchergebnissen angezeigt wird, wählen Sie die **OK** Schaltfläche.  
  
4.  In der **herunterladen und installieren** Begriffe (Dialogfeld), wenn Sie die Lizenzierung zustimmen, wählen Sie die **installieren** Schaltfläche.  
  
5.  Nachdem die Vorlage installiert wurde, ein Projekt erstellen, indem Sie auswählen **Datei**, **neues Projekt**, und wählen Sie dann die `WRLClassLibrary` Vorlage. Das Projekt erstellt eine DLL.  
  
## <a name="examples-that-use-the-project-template"></a>Beispiele, in denen die Projektvorlage  
 Lesen [Exemplarische Vorgehensweise: Erstellen einer grundlegenden Komponente für die Windows-Runtime](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) für ein Beispiel, das diese Vorlage zum Erstellen einer Windows-Runtime-Komponente verwendet.  
  
## <a name="what-the-project-template-provides"></a>Was die Projektvorlage enthält  
 Die Projektvorlage stellt Folgendes bereit:  
  
-   eine IDL-Datei, die die MIDL-Attribute für eine Basisschnittstelle seine Implementierung der Klasse deklariert. Im Folgenden ein Beispiel:  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   eine CPP-Datei, die die Implementierung der Klasse definiert. Im Folgenden ein Beispiel:  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     Die [RuntimeClass](../windows/runtimeclass-class.md) Basisklasse hilft bei der Verwaltung des globalen Verweis aller Objekte im Modul und deklariert die Methoden der [IUnknown](http://msdn.microsoft.com/en-us/33f1d79a-33fc-4ce5-a372-e08bda378332) und ["iinspectable"](http://msdn.microsoft.com/en-us/0657e51f-d4c0-46c6-927d-b01e54b6846c) Schnittstellen. Die [InspectableClass](../windows/inspectableclass-macro.md) -Makro implementiert `IUnknown` und `IInspectable`. Die [ActivatableClass](../windows/activatableclass-macros.md) Makro erstellt eine Klassenfactory, die Instanzen der Klasse erstellt.  
  
-   exportiert eine Datei namens module.cpp, die die Bibliothek definiert `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory`, und `DllGetClassObject`.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Vorlagenbibliothek für Windows-Runtime (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)