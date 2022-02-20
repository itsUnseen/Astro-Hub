math.randomseed(tick());
local modules, controlfunc;
for i,v in next, getgc(true) do
    if type(v) == "table" then
        if rawget(v, "Version") and rawget(v, "Kitty") then
            local mt = getrawmetatable(v);
            modules = select(2, pcall(getupvalue, mt.__index, 1)); --gets the ts module (haha totally not stolen from kiriot :p)
        elseif rawget(v, "Control") and type(rawget(v, "Control")) == "function" then
            controlfunc = rawget(v, "Control"); --control function used for walkspeed mult
        end
    end
    if modules and controlfunc then break; end
end
if not modules or (modules and not rawget(modules, "Network")) then
    print("Failed To Get TS Module"); -- :(
    return;
end
if not controlfunc then
    print("Failed To Get Control Function"); -- :(
    return;
end

return modules, controlfunc
