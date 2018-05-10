---
title: Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [Visual Studio], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c82e41544bde9cdd945e23f4ea5884e4e76ae22b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="creating-a-new-custom-or-data-resource"></a>Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource
Sie können eine neue benutzerdefinierte oder Datenressource erstellen, indem Sie die Ressource mithilfe der normalen Syntax von Ressourcenskriptdateien (RC) in einer separaten Datei platzieren und dann die Datei einschließen, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt und dann im Kontextmenü auf **Ressourcenincludes** klicken.  
  
### <a name="to-create-a-new-custom-or-data-resource"></a>So erstellen Sie eine neue benutzerdefinierte oder Datenressource  
  
1. [Erstellen Sie eine RC-Datei](../windows/how-to-create-a-resource-script-file.md) , die die benutzerdefinierte oder Datenressource enthält.  
  
     Sie können benutzerdefinierte Daten in einer RC-Datei als in Anführungszeichen eingeschlossene nullterminierte Zeichenfolgen oder als ganze Zahlen im dezimalen, hexadezimalen oder oktalen Format eingeben.  
  
2.  Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die RC-Datei Ihres Projekts, und klicken Sie dann im Kontextmenü auf **Ressourcenincludes** .  
  
3.  Geben Sie im Feld **Kompilierzeitdirektiven** eine **#include** -Anweisung ein, die den Namen der Datei angibt, die Ihre benutzerdefinierte Ressource enthält. Zum Beispiel:  
  
 ```  
    #include mydata.rc  
 ```  
  
     Achten Sie auf die korrekte Syntax und Rechtschreibung Ihrer Eingaben. Der Inhalt des Felds **Kompilierzeitdirektiven** wird in die Ressourcenskriptdatei genau so eingefügt, wie sie ihn eingegeben haben.  
  
4.  Klicken Sie auf **OK** , um Ihre Änderungen aufzuzeichnen.  
  
 Eine weitere Möglichkeit zum Erstellen einer benutzerdefinierten Ressource ist das Importieren einer externen Datei als benutzerdefinierte Ressource. Weitere Informationen finden Sie unter [Importieren und Exportieren von Ressourcen](../windows/how-to-import-and-export-resources.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Binary Editor](binary-editor.md)

