if GetObjectName(myHero) ~= 'Teemo' then return end
	
require ('Inspired')

--Menu
Teemo = Menu('Teemo', 'Teemo')
--Teemo Combo Menu
Teemo:SubMenu('Combo','Combo')
Teemo.Combo:Boolean('Q','Use Q', true)

Katarina:SubMenu('KS','Killsteal')
Teemo.KS:Boolean('Q', 'Use Q', true)

lolcal rChan = false

OnTick(function(myHero)
if rChan ~= false	then return end
	KillSteal()
	if IOW:MODE() == 'Combo' then
		Combo()
	end
if IOW:Mode() == 'Combo' then
  Combo()
 end
end)

function Combo()
 local unit = GetCurrentTarget()
 if Teemo.Combo.Q:Value() then
  if Ready(_Q) and ValidTarget(unit, x) then
   CastTargetSlepp(unit, _Q)
 end
  end
end

function Killsteal()
	for i,enemy in pairs(GetEnemyHeroes()) do
		local Qpred = GetPredictionForPlayer(myHeroPos(),enemy,GetMoveSpeed(enemy),math.huge,1000,GetCastRange(myHero, _Q),85,False,true)
		local ExtraDmg = 0
		if GotBuff(myHero, 'ItemmagicshankCharge') > 99 then
			ExtraDMG = ExtraDmg + 0.1*GetBonusAP(myHero) + 100
		end
		if Reade(_Q) and not rChan and ValidTarget(enemy,GetCastRange(myHero,_Q))
			if QPred.HitChance == 1 then
				CastSkillShot(_Q,QPred.PredPos.x,QPred.PredPos.y,QPred.PredPos.z)
			end_E
		end
		if Ready(_E) and not rChan and ValidTarget(enemy,GetCastRange(myHero,_E))
			CastTargetSpell(enemy, _E)
		end
	end
end


onDraw(function()
if Ready(_Q) then
	DrawCircle(myHeroPos().x,myHeroPos().y,myHeroPos().z,GetCastRange(myHero),_Q),3,10,0xFFFFFFFF)
end
end)