//设置生成的随机json数量
let num = 50;
//设置生成的json的名称
let name = "random_json";


//设置保存路径
const lujin = "/storage/emulated/0/json_random/";

//开始循环
for (let i = 0; i < num; i++) {
    //随机xyz轴，并限制范围
    const x = ((Math.random() - 0.5) * 6000).toFixed(6);
    const z = (Math.random() * 600 - 300).toFixed(6);
    const y = ((Math.random() - 0.5) * 6000).toFixed(6);
    //创建新的jsoncontent对象
    const jsonc = {
        description: "",
        name: `${name}${i+1}`,
        position: [parseFloat(x), parseFloat(z), parseFloat(y)]
    };

    //设置保存路径
    const path = `${lujin}${name}${i+1}.json`;
    //创建json文件，并写入内容
    files.write(path, JSON.stringify(jsonc), "utf-8");
}
