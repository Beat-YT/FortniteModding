## Example c++ classes.

FortInventory
```
// Fill out your copyright notice in the Description page of Project Settings.


#pragma once

#include "CoreMinimal.h"
#include "FortPickup.h"
#include "GameFramework/Actor.h"
#include "FortInventory.generated.h"

USTRUCT(Blueprintable)
struct FFortItemList : public FFastArraySerializer
{
	GENERATED_BODY()

		UPROPERTY(EditAnywhere, BlueprintReadWrite)
	TArray<struct FFortItemEntry>                      ReplicatedEntries;                                        // 0x00B0(0x0010) (ZeroConstructor, SaveGame)
	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	TArray<class UFortWorldItem*>                      ItemInstances;                                            // 0x0110(0x0010) (ZeroConstructor)
};

UCLASS()
class FORTNITEGAME_API AFortInventory : public AActor
{

	UFUNCTION(BlueprintCallable)
	void HandleInventoryLocalUpdate();

	GENERATED_BODY()
	
public:	

	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	struct FFortItemList                               Inventory;

	// Sets default values for this actor's properties
	AFortInventory();

protected:
	// Called when the game starts or when spawned
	virtual void BeginPlay() override;

public:	
	// Called every frame
	virtual void Tick(float DeltaTime) override;

	
	
};

```
