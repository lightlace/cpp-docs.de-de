---
title: 'Vorgehensweise: Erstellen und Verwenden von Weak_ptr-Instanzen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e51e523540e14905bef17edd52205c4d2102afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-and-use-weakptr-instances"></a>Gewusst wie: Erstellen und Verwenden von weak_ptr-Instanzen
Manchmal muss ein Objekt eine Möglichkeit speichern, um auf das `shared_ptr` zugrunde liegende Objekt zuzugreifen, ohne dadurch den Referenzzähler zu erhöhen. Diese Situation tritt in der Regel auf, wenn zyklische Verweise zwischen `shared_ptr`-Instanzen vorliegen.  
  
 Der optimale Entwurf ist die Vermeidung von gemeinsamem Zeigerbesitz. Wenn Sie jedoch gemeinsamen Besitz von `shared_ptr`-Instanzen benötigen, vermeiden Sie zyklische Verweise zwischen ihnen. Wenn zyklische Verweise unvermeidbar oder aus irgendeinem Grund sogar vorzuziehen sind, verwenden Sie `weak_ptr`, um einem oder mehreren der Besitzer einen schwachen Verweis auf einen anderen `shared_ptr` zu geben. Mit `weak_ptr` können Sie einen `shared_ptr` erstellen, der eine vorhandene Gruppe verwandter Instanzen verknüpft, wobei nur die zugrunde liegende Speicherressource weiterhin gültig ist. Der `weak_ptr` selbst nimmt nicht an der Referenzzählung teil und kann daher nicht verhindern, dass der Referenzzähler den Wert 0 erreicht. Sie können jedoch einen `weak_ptr` verwenden, um zu versuchen, eine neue Kopie des `shared_ptr` zu erhalten, mit der er initialisiert wurde. Wenn der Arbeitsspeicher bereits gelöscht wurde, eine **Bad_weak_ptr** Ausnahme wird ausgelöst. Wenn der Arbeitsspeicher noch gültig ist, erhöht der neue freigegebene Zeiger den Verweiszähler und stellt sicher, dass der Arbeitsspeicher gültig bleibt, solange die `shared_ptr`-Variable im Gültigkeitsbereich liegt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt einen Fall, in dem `weak_ptr` verwendet wird, um das richtige Löschen von Objekten sicherzustellen, die Ringabhängigkeiten aufweisen. Nehmen Sie für das Beispiel an, dass es erst erstellt wurde, nachdem keine alternativen Lösungen gefunden werden konnten. Die `Controller`-Objekte stellen einige Aspekte eines Computerprozesses dar, und sie funktionieren unabhängig. Jeder Controller muss in der Lage sein, den Status der anderen Controller jederzeit abzufragen, und jeder enthält zu diesem Zweck einen privaten `vector<weak_ptr<Controller>>`. Jeder Vektor enthält einen Zirkelverweis. Daher werden `weak_ptr`-Instanzen anstelle von `shared_ptr` verwendet.  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
```Output  
Creating Controller0Creating Controller1Creating Controller2Creating Controller3Creating Controller4push_back to v[0]: 1push_back to v[0]: 2push_back to v[0]: 3push_back to v[0]: 4push_back to v[1]: 0push_back to v[1]: 2push_back to v[1]: 3push_back to v[1]: 4push_back to v[2]: 0push_back to v[2]: 1push_back to v[2]: 3push_back to v[2]: 4push_back to v[3]: 0push_back to v[3]: 1push_back to v[3]: 2push_back to v[3]: 4push_back to v[4]: 0push_back to v[4]: 1push_back to v[4]: 2push_back to v[4]: 3use_count = 1Status of 1 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 3 = OnDestroying Controller0Destroying Controller1Destroying Controller2Destroying Controller3Destroying Controller4Press any key  
```  
  
 Ändern Sie testweise den Vektor `others` in einen `vector<shared_ptr<Controller>>`, und beachten Sie dann in der Ausgabe, dass keine Destruktoren aufgerufen wurden, als `TestRun` zurückkehrte.  
  
## <a name="see-also"></a>Siehe auch  
 [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)