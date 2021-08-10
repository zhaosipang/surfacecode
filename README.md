# surfacecode
Code for handling surface experiments
# Categorize the order of experiments
% 
namelist=[{'zhaona'}];
for nameId =1:length(namelist)
    name = namelist{nameId};
    load([name 'real_three_Exp.mat']);
    surface_EXP = [];
    volume_EXP = [];
    speed_EXP = [];
    for block = 1:length(real_three_Exp)
        if real_three_Exp(block) == 1
            surface_EXP = [surface_EXP;block];
        elseif real_three_Exp(block) == 2
            volume_EXP = [volume_EXP;block];
            elses
            speed_EXP = [speed_EXP;block];
        end
        
    end
    
    savename = [name ' experience_order'];
    path=pwd;
    index_dir=strfind(path,'/');
    path_temp=path(1:index_dir(end)-1);
    save([path_temp '/experience_order/' name '.mat'],'surface_EXP','volume_EXP','speed_EXP');
 vvv
end
