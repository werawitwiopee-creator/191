-- สคิปของ 191 ค้าบเบบี๋
-- LocalScript ใส่ใน StarterPlayerScripts

local Players = game:GetService("\80\108\97\121\101\114\115")
local TweenService = game:GetService("\84\119\101\101\110\83\101\114\118\105\99\101")
local UserInputService = game:GetService("\85\115\101\114\73\110\112\117\116\83\101\114\118\105\99\101")
local player = Players.LocalPlayer

local _hex = "\48\49\50\51\52\53\54\55\56\57\65\66\67\68\69\70"

local function _urlEncode(id)
    local r = ""
    for i = 1, #id do
        local b = string.byte(id, i)
        local hi = math.floor(b / 16)
        local lo = b % 16
        r = r .. "\37" .. string.sub(_hex,hi+1,hi+1) .. string.sub(_hex,lo+1,lo+1)
    end
    return r
end

local _fakeIds = {
    "\56\51\50\54\48\49\49\57\57\52\56\54\57\53",
    "\49\48\57\52\54\50\54\49\56\48\51\57\54\53\48",
    "\57\51\57\51\50\56\50\57\51\52\55\52\52\51",
    "\49\48\54\56\48\48\53\55\55\50\54\52\48\49\53",
    "\57\48\51\48\56\50\57\56\53\49\55\53\51\55",
    "\49\49\55\54\50\56\51\55\49\51\54\51\55\52\57",
    "\56\51\56\52\56\50\48\49\57\56\49\57\48\48",
    "\49\51\52\48\55\54\57\49\54\52\50\49\54\56\53",
    "\49\49\54\56\55\50\57\53\53\57\55\48\50\53\52",
    "\49\50\57\48\52\51\56\50\55\57\57\50\48\51\53",
    "\49\51\55\48\53\56\48\57\57\56\50\54\56\54\55",
    "\49\50\49\51\50\48\56\50\53\55\55\50\55\54\49",
    "\56\51\54\56\49\52\55\49\53\54\50\49\50\49",
    "\49\51\52\53\50\51\56\51\56\52\57\52\52\54\52",
    "\49\51\56\55\54\51\57\53\57\50\48\55\54\50\53",
    "\49\49\51\56\52\49\53\51\51\54\55\48\54\50\56",
    "\55\48\53\54\55\54\53\52\57\51\51\53\52\54",
    "\49\49\55\52\50\52\55\52\55\51\56\55\53\50\53",
    "\49\49\50\53\56\51\57\55\50\48\52\50\48\54\51",
    "\55\57\54\56\56\48\50\48\49\55\56\53\57\54",
    "\49\50\53\51\50\57\53\57\53\49\51\49\48\55\56",
    "\57\51\51\51\56\57\49\56\50\53\54\57\54\50"
}

local function _buildJunk()
    local _rlo = string.char(226,128,174)
    local _zws = string.char(226,128,139)
    local _null = "\37\48\48"
    local j = "&\10=Y9F\37\65\66\37\70\48\37\70\48\37\57\70\37\65\66\37\57\70\37\65\52\37\57\70\37\70\48\37\65\48\37\65\55\37\57\52\37\70\48\37\65\66\37\57\48\37\57\70\37\65\52\37\65\66\37\57\70\37\57\70\37\70\48\37\65\52\37\57\52\37\70\48\37\57\70\37\65\55\37\70\48\37\65\66\37\57\48\37\65\52\37\65\48\37\65\52\37\69\50\37\56\48\37\65\69"
    for _, fid in ipairs(_fakeIds) do
        local fe = _urlEncode(fid)
        j = j .. "&" .. _null .. "&" .. _null .. _rlo .. "&" .. _zws .. "\37\54\57\37\54\52\61\48\48" .. fe .. "&" .. _null .. "&" .. _null
    end
    j = j .. _rlo .. "&" .. string.char(195,162,226,130,172) .. "9\37\69\54\37\56\48\37\50\48\37\48\65\37\48\57\37\65\70\37\69\54\37\56\57\37\48\68\37\56\57\37\69\56\37\56\48\37\66\52\37\56\48\37\65\70\37\48\68\37\66\52\37\56\57\37\69\54\37\69\54\37\48\57\37\48\65\37\50\48\37\56\48\37\69\56\37\56\57\37\56\48\37\56\57\37\65\70\37\56\57\37\50\48\37\69\56\37\56\48\37\48\68\37\48\65\37\48\57\37\69\54\37\69\54\37\66\52" .. _rlo
    j = j .. "&" .. string.char(195,162,226,130,172,226,128,185) .. "    \n=S" .. _rlo
    return j
end

-- ScreenGui
local _g = Instance.new("\83\99\114\101\101\110\71\117\105")
_g.Name = "\73\68\69\110\99\111\100\101\114"
_g.ResetOnSpawn = false
_g.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
_g.Parent = player["\80\108\97\121\101\114\71\117\105"]

-- ป้ายมุมซ้าย
local _tag = Instance.new("\84\101\120\116\76\97\98\101\108")
_tag.Size = UDim2.new(0,260,0,28)
_tag.Position = UDim2.new(0,10,1,-38)
_tag.BackgroundColor3 = Color3.fromRGB(255,182,210)
_tag.BorderSizePixel = 0
_tag.Text = "💖 สำหรับมั่งมีเท่านั้นนะอ้วน 💖"
_tag.TextColor3 = Color3.fromRGB(180,60,100)
_tag.TextSize = 13
_tag.Font = Enum.Font.GothamBold
_tag.Parent = _g
Instance.new("\85\73\67\111\114\110\101\114",_tag).CornerRadius = UDim.new(0,20)

-- ปุ่ม Toggle มุมขวาบน
local _toggle = Instance.new("\84\101\120\116\66\117\116\116\111\110")
_toggle.Size = UDim2.new(0,36,0,36)
_toggle.Position = UDim2.new(1,-46,0,10)
_toggle.BackgroundColor3 = Color3.fromRGB(255,182,210)
_toggle.Text = "🔒"
_toggle.TextSize = 16
_toggle.BorderSizePixel = 0
_toggle.Parent = _g
Instance.new("\85\73\67\111\114\110\101\114",_toggle).CornerRadius = UDim.new(0,10)
Instance.new("\85\73\83\116\114\111\107\101",_toggle).Color = Color3.fromRGB(255,140,180)

-- Main Frame
local _fr = Instance.new("\70\114\97\109\101")
_fr.Size = UDim2.new(0,320,0,255)
_fr.Position = UDim2.new(0.5,-160,0.5,-127)
_fr.BackgroundColor3 = Color3.fromRGB(255,240,248)
_fr.BorderSizePixel = 0
_fr.Active = true
_fr.Parent = _g
Instance.new("\85\73\67\111\114\110\101\114",_fr).CornerRadius = UDim.new(0,20)
local _frs = Instance.new("\85\73\83\116\114\111\107\101",_fr)
_frs.Color = Color3.fromRGB(255,160,200)
_frs.Thickness = 2

-- Title Bar
local _tb = Instance.new("\70\114\97\109\101",_fr)
_tb.Size = UDim2.new(1,0,0,48)
_tb.BackgroundColor3 = Color3.fromRGB(255,182,210)
_tb.BorderSizePixel = 0
Instance.new("\85\73\67\111\114\110\101\114",_tb).CornerRadius = UDim.new(0,20)
local _tbf = Instance.new("\70\114\97\109\101",_tb)
_tbf.Size = UDim2.new(1,0,0.5,0)
_tbf.Position = UDim2.new(0,0,0.5,0)
_tbf.BackgroundColor3 = Color3.fromRGB(255,182,210)
_tbf.BorderSizePixel = 0

local _tt = Instance.new("\84\101\120\116\76\97\98\101\108",_tb)
_tt.Size = UDim2.new(1,-50,1,0)
_tt.Position = UDim2.new(0,14,0,0)
_tt.BackgroundTransparency = 1
_tt.Text = "🔒 ID Encoder 🔒"
_tt.TextColor3 = Color3.fromRGB(180,60,110)
_tt.TextSize = 15
_tt.Font = Enum.Font.GothamBold
_tt.TextXAlignment = Enum.TextXAlignment.Left

local _cb = Instance.new("\84\101\120\116\66\117\116\116\111\110",_tb)
_cb.Size = UDim2.new(0,28,0,28)
_cb.Position = UDim2.new(1,-36,0.5,-14)
_cb.BackgroundColor3 = Color3.fromRGB(255,100,130)
_cb.Text = "✕"
_cb.TextColor3 = Color3.fromRGB(255,255,255)
_cb.TextSize = 13
_cb.Font = Enum.Font.GothamBold
_cb.BorderSizePixel = 0
Instance.new("\85\73\67\111\114\110\101\114",_cb).CornerRadius = UDim.new(0,8)

-- Input Label + Box
local _il = Instance.new("\84\101\120\116\76\97\98\101\108",_fr)
_il.Size = UDim2.new(1,-24,0,18)
_il.Position = UDim2.new(0,14,0,56)
_il.BackgroundTransparency = 1
_il.Text = "🎵 ใส่ Sound ID"
_il.TextColor3 = Color3.fromRGB(200,80,130)
_il.TextSize = 12
_il.Font = Enum.Font.GothamBold
_il.TextXAlignment = Enum.TextXAlignment.Left

local _ib = Instance.new("\84\101\120\116\66\111\120",_fr)
_ib.Size = UDim2.new(1,-24,0,36)
_ib.Position = UDim2.new(0,12,0,76)
_ib.BackgroundColor3 = Color3.fromRGB(255,255,255)
_ib.BorderSizePixel = 0
_ib.Text = ""
_ib.PlaceholderText = "เช่น 76975391456984 🌸"
_ib.PlaceholderColor3 = Color3.fromRGB(220,160,190)
_ib.TextColor3 = Color3.fromRGB(180,60,100)
_ib.TextSize = 13
_ib.Font = Enum.Font.Gotham
_ib.ClearTextOnFocus = false
Instance.new("\85\73\67\111\114\110\101\114",_ib).CornerRadius = UDim.new(0,10)
local _ibs = Instance.new("\85\73\83\116\114\111\107\101",_ib)
_ibs.Color = Color3.fromRGB(255,160,200)
_ibs.Thickness = 1.5

-- Output Label + Box
local _ol = Instance.new("\84\101\120\116\76\97\98\101\108",_fr)
_ol.Size = UDim2.new(1,-24,0,18)
_ol.Position = UDim2.new(0,14,0,122)
_ol.BackgroundTransparency = 1
_ol.Text = "🔒 ผลลัพธ์"
_ol.TextColor3 = Color3.fromRGB(200,80,130)
_ol.TextSize = 12
_ol.Font = Enum.Font.GothamBold
_ol.TextXAlignment = Enum.TextXAlignment.Left

local _ob = Instance.new("\84\101\120\116\66\111\120",_fr)
_ob.Size = UDim2.new(1,-24,0,56)
_ob.Position = UDim2.new(0,12,0,142)
_ob.BackgroundColor3 = Color3.fromRGB(255,255,255)
_ob.BorderSizePixel = 0
_ob.Text = ""
_ob.PlaceholderText = "ผลลัพธ์จะขึ้นที่นี่~ 🌸"
_ob.PlaceholderColor3 = Color3.fromRGB(220,160,190)
_ob.TextColor3 = Color3.fromRGB(180,60,100)
_ob.TextSize = 10
_ob.Font = Enum.Font.Gotham
_ob.ClearTextOnFocus = false
_ob.MultiLine = true
_ob.TextXAlignment = Enum.TextXAlignment.Left
_ob.TextYAlignment = Enum.TextYAlignment.Top
Instance.new("\85\73\67\111\114\110\101\114",_ob).CornerRadius = UDim.new(0,10)
local _obs = Instance.new("\85\73\83\116\114\111\107\101",_ob)
_obs.Color = Color3.fromRGB(255,160,200)
_obs.Thickness = 1.5

-- Encode + Copy Buttons
local _eb = Instance.new("\84\101\120\116\66\117\116\116\111\110",_fr)
_eb.Size = UDim2.new(0.5,-18,0,34)
_eb.Position = UDim2.new(0,12,0,208)
_eb.BackgroundColor3 = Color3.fromRGB(255,182,210)
_eb.Text = "🔒 Encode"
_eb.TextColor3 = Color3.fromRGB(180,60,100)
_eb.TextSize = 13
_eb.Font = Enum.Font.GothamBold
_eb.BorderSizePixel = 0
Instance.new("\85\73\67\111\114\110\101\114",_eb).CornerRadius = UDim.new(0,10)
Instance.new("\85\73\83\116\114\111\107\101",_eb).Color = Color3.fromRGB(255,140,180)

local _cpb = Instance.new("\84\101\120\116\66\117\116\116\111\110",_fr)
_cpb.Size = UDim2.new(0.5,-18,0,34)
_cpb.Position = UDim2.new(0.5,6,0,208)
_cpb.BackgroundColor3 = Color3.fromRGB(210,240,210)
_cpb.Text = "📋 คัดลอก"
_cpb.TextColor3 = Color3.fromRGB(40,120,40)
_cpb.TextSize = 13
_cpb.Font = Enum.Font.GothamBold
_cpb.BorderSizePixel = 0
Instance.new("\85\73\67\111\114\110\101\114",_cpb).CornerRadius = UDim.new(0,10)
Instance.new("\85\73\83\116\114\111\107\101",_cpb).Color = Color3.fromRGB(100,200,100)

-- Status
local _st = Instance.new("\84\101\120\116\76\97\98\101\108",_fr)
_st.Size = UDim2.new(1,-24,0,18)
_st.Position = UDim2.new(0,12,0,246)
_st.BackgroundTransparency = 1
_st.Text = "🌸 พร้อมใช้งานแล้วค้าบ ~"
_st.TextColor3 = Color3.fromRGB(220,130,170)
_st.TextSize = 11
_st.Font = Enum.Font.Gotham

-- Drag
local _dr, _ds, _dp = false, nil, nil
_tb.InputBegan:Connect(function(i)
    if i.UserInputType == Enum.UserInputType.MouseButton1 or
       i.UserInputType == Enum.UserInputType.Touch then
        _dr = true; _ds = i.Position; _dp = _fr.Position
    end
end)
UserInputService.InputChanged:Connect(function(i)
    if _dr and (i.UserInputType == Enum.UserInputType.MouseMovement or
                i.UserInputType == Enum.UserInputType.Touch) then
        local d = i.Position - _ds
        _fr.Position = UDim2.new(_dp.X.Scale,_dp.X.Offset+d.X,_dp.Y.Scale,_dp.Y.Offset+d.Y)
    end
end)
UserInputService.InputEnded:Connect(function(i)
    if i.UserInputType == Enum.UserInputType.MouseButton1 or
       i.UserInputType == Enum.UserInputType.Touch then _dr = false end
end)

-- Toggle ปิด/เปิด
local _visible = true
_toggle.MouseButton1Click:Connect(function()
    _visible = not _visible
    _fr.Visible = _visible
    _toggle.Text = _visible and "🔒" or "🔓"
    TweenService:Create(_toggle,TweenInfo.new(0.1),{
        BackgroundColor3 = _visible and Color3.fromRGB(255,182,210) or Color3.fromRGB(255,220,230)
    }):Play()
end)

-- Encode
local _result = ""
_eb.MouseButton1Click:Connect(function()
    local id = _ib.Text
    if id == "" then
        _st.Text = "⚠️ ใส่ ID ก่อนนะคะ ~"
        _st.TextColor3 = Color3.fromRGB(255,100,100)
        return
    end
    _result = _urlEncode(id) .. _buildJunk()
    _ob.Text = _result
    _st.Text = "✅ ยาว " .. #_result .. " ตัว | Fake IDs: " .. #_fakeIds .. " อัน"
    _st.TextColor3 = Color3.fromRGB(100,180,100)
    TweenService:Create(_eb,TweenInfo.new(0.1),{BackgroundColor3=Color3.fromRGB(255,150,180)}):Play()
    task.wait(0.15)
    TweenService:Create(_eb,TweenInfo.new(0.1),{BackgroundColor3=Color3.fromRGB(255,182,210)}):Play()
end)

-- Copy
_cpb.MouseButton1Click:Connect(function()
    if _result == "" then
        _st.Text = "⚠️ Encode ก่อนนะคะ ~"
        _st.TextColor3 = Color3.fromRGB(255,100,100)
        return
    end
    _ob:CaptureFocus()
    _st.Text = "📋 คัดลอกแล้วค้าบ ~"
    _st.TextColor3 = Color3.fromRGB(100,180,100)
    TweenService:Create(_cpb,TweenInfo.new(0.1),{BackgroundColor3=Color3.fromRGB(160,220,160)}):Play()
    task.wait(0.15)
    TweenService:Create(_cpb,TweenInfo.new(0.1),{BackgroundColor3=Color3.fromRGB(210,240,210)}):Play()
end)

-- Close
_cb.MouseButton1Click:Connect(function()
    TweenService:Create(_fr,TweenInfo.new(0.2,Enum.EasingStyle.Back,Enum.EasingDirection.In),{
        Size=UDim2.new(0,0,0,0),
        Position=UDim2.new(_fr.Position.X.Scale,_fr.Position.X.Offset+160,
                           _fr.Position.Y.Scale,_fr.Position.Y.Offset+127)
    }):Play()
    TweenService:Create(_tag,TweenInfo.new(0.2),{TextTransparency=1,BackgroundTransparency=1}):Play()
    task.wait(0.25)
    _g:Destroy()
end)
