if saved and saved.lasttimewassaved == true then
		if saved["Sniper"] then
			for k, v in pairs(saved["Sniper"]) do currentSettings["Sniper"][k] = v end
		end
		if saved["G36"] then
			for k, v in pairs(saved["G36"]) do currentSettings["G36"][k] = v end
		end

		applyWeaponSettings(currentSettings)

		local isMobile = UserInputService.TouchEnabled and not UserInputService.KeyboardEnabled
		if isMobile then
			showNotification("تم تشغيل الاعدادات الماضية. اذا كنت تريد تغييرها اضغط ضغطة مطولة على الشاشة لمدة 5 ثواني.")
		else
			showNotification("تم تشغيل الاعدادات الماضية. اذا كنت تريد تغييرها اضغط زر B.")
		end
	else
		task.wait(0.5)
		buildUI()
	end
end
