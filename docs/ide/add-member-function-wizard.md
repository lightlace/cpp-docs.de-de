---
title: Asssistent zum Hinzufügen von | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.function.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 488c7ca455b267a79b0d2906849596346a191792
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="add-member-function-wizard"></a>Assistent zum Hinzufügen von Memberfunktionen
Dieser Assistent fügt die Deklaration einer Memberfunktion die Headerdatei und Stub-Memberimplementierung-Funktion der Implementierungsdatei für die ausgewählte Klasse.  
  
 Nachdem Sie die Memberfunktion mit dem Assistenten hinzugefügt haben, können Sie den Code in der Entwicklungsumgebung bearbeiten.  
  
 **Rückgabetyp**  
 Legt den Rückgabetyp für die Member-Funktion, die Sie hinzufügen. Können Sie Ihre eigenen Rückgabetyp angeben, oder Sie können aus der Liste der verfügbaren Typen auswählen. Informationen zu den Typen finden Sie unter [grundlegende Typen](../cpp/fundamental-types-cpp.md).  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **Funktionsname**  
 Legt den Namen der Memberfunktion, die Sie hinzufügen.  
  
 **Parametertyp**  
 Legt den Typ des Parameters, die Sie für die Member-Funktion hinzufügen fest, wenn die Memberfunktion über Parameter verfügt. Sie können Ihren eigenen Parametertyp bereitstellen oder können Sie aus der Liste der verfügbaren Typen auswählen.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **Parametername**  
 Legt den Namen eines Parameters, die Sie für die Member-Funktion hinzufügen fest, wenn die Memberfunktion über Parameter verfügt.  
  
 **Parameterliste**  
 Zeigt eine Liste der Parameter, mit denen, die Sie die Member-Funktion hinzugefügt haben. Um einen Parameter zur Liste hinzuzufügen, geben Sie einen Typ aus, und nennen Sie der **Parametertyp** und **Parametername** Kontrollkästchen und klicken Sie auf **hinzufügen**. Um einen Parameter aus der Liste zu entfernen, wählen Sie den Parameter, und klicken Sie auf **entfernen**.  
  
 **Zugriff**  
 Legt den Zugriff auf die Member-Funktion fest. Zugriffsmodifizierer sind Schlüsselwörter, die den Zugriff angeben, den andere Klassen auf die Member-Funktion haben. Finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) für Weitere Informationen zum Zugriff angeben. Die Zugriffsebene des Members-Funktion festgelegt ist, um **öffentlichen** standardmäßig.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 Überprüfen Sie, ob die neue Member-Funktion statisch oder virtuell ist, und gibt an, ob es Inline ist oder reinen. Wenn Sie festlegen, dass der als reine Memberfunktion, die `Virtual` Kontrollkästchen ausgewählt ist, und die **Inline** Kontrollkästchen nicht mehr verfügbar ist. Der Standardwert ist eine nicht statische, nicht virtuelle Memberfunktion.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|[Static](../cpp/storage-classes-cpp.md)|Gibt an, dass die Funktion verhält sich wie ein globaler und außerhalb der Klasse, selbst bei keine Klasseninstanziierung aufgerufen werden kann. Die Memberfunktion hat keinen Zugriff auf nicht statische Member. Eine Memberfunktion, angegeben als `Static` nicht virtuell sein.|  
|[Virtuelle](../cpp/virtual-cpp.md)|Stellt sicher, dass die richtige Memberfunktion für ein Objekt, unabhängig von der Ausdruck verwendet, um die Member-Funktion aufrufen, aufgerufen wird. Eine Memberfunktion, angegeben als `Virtual` kann nicht statisch sein.|  
|**Reine**|Gibt an, keine Implementierung angegeben wird, für die virtuelle Memberfunktion, die deklariert wird. aus diesem Grund **reiner** kann nur für virtuelle Memberfunktionen angegeben werden. Eine Klasse enthält mindestens eine reine virtuelle Memberfunktion ist eine abstrakte Klasse angesehen. Von der abstrakten Klasse abgeleitete Klassen müssen die rein virtuelle Memberfunktion implementieren oder sie sich, auch abstrakte Klassen.|  
|[Inline](../cpp/inline-functions-cpp.md)|Weist den Compiler an, eine Kopie des Elements Funktionstexts an jeder Stelle einzufügen, der die Memberfunktion aufgerufen wird. Eine Memberfunktion, angegeben als **Inline** kann nicht rein sein.|  
  
 **CPP-Datei**  
 Legt den Speicherort der Datei, in denen die Implementierung der Stub-Memberfunktion geschrieben wird. Standardmäßig ist es in der CPP-Datei für die Klasse geschrieben, der die Member-Funktion hinzugefügt wird. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen zu ändern. Die Implementierung der Memberfunktion wird auf den Inhalt der ausgewählten Datei hinzugefügt.  
  
 **Kommentar**  
 Stellt einen Kommentar in der Headerdatei für die Member-Funktion.  
  
 **Funktionssignatur**  
 Die Memberfunktion zeigt, wie er im Code angezeigt wird, wenn Sie auf **Fertig stellen**. Sie können der Text in diesem Feld nicht bearbeiten. Um die Member-Funktion zu ändern, ändern Sie die entsprechenden Felder im Assistenten aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)