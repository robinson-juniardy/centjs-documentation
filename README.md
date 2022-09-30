# CentJS API Framework

**CentJS API Framework** is a collection of libraries to create a starter kit for your api project, made using modules from express js and others, for more details you can follow the following documentation steps.


## Create Your First CentJS Project

>***The first thing*** you have to do to create a project from **CentJS** is to install the cli package from CentJS, follow this steps.
>> **open yor command line and follow instructions bellow**
>>* install cent js cli for a global :
>> **`npm install -g @centjs/cli`**
>>* create a new project :
>> **`cent create:app`**
>> * start server
>> **`cent serve`**  or  **`npm run dev`**

## Project Structure
> 📦src  
 ┣ 📂app  
 ┃ ┣ 📂config  
 ┃ ┣ 📂controller  
 ┃ ┃ ┣ 📂greeting  
 ┃ ┃ ┃ ┗ 📜hello.controller.ts 
 ┃ ┃ ┣ 📂welcome  
 ┃ ┃ ┃ ┗ 📜welcome.controller.ts  
 ┃ ┃ ┗ 📂whisper  
 ┃ ┃ ┃ ┗ 📜whisper.controller.ts  
 ┃ ┣ 📂data  
 ┃ ┃ ┗ 📜cent.database.ts  
 ┃ ┣ 📂model  
 ┃ ┃ ┗ 📂auth  
 ┃ ┃ ┃ ┗ 📜login.model.ts  
 ┃ ┣ 📂services  
 ┃ ┗ 📂utils  
 ┗ 📜index.ts

> **`files created in the folder structure are just examples`**

## Controllers
the controller is needed to make api routing along with the response data to be sent, here is the explanation,   
*the controller structure has the name of the module in which it stores the controller file*, **for example**:
>┣ 📂controller  -> `controller folder`
┃ ┃ ┣ 📂greeting -> `module name`
┃ ┃ ┃ ┗ 📜hello.controller.ts -> `controller name`

for best practice you can using **cent cli** for generate controller
`cent make:controller greeting/hello`

Or you can create a controller manually with the following basic code

**Import Dependencies Of Module From CentJS Library**
```typescript
import Cent, {
Controller,
Get,
Post,
Put,
Patch,
Delete,
Request,
Response,
Next,
} from "@centjs/core";
import * as CentOrm from "@centjs/orm";
```
**Create Class Of Controller**
```typescript 
@Controller("/welcome", [myMiddleware]) // basic routing (module_path_url, middleware?: Array)
export default class Welcome_Controller {
	
	@Get("/", [middlewareFormData]) // define get method (api_path_url, middleware?: Array)
	public welcomeMessage(request: Request, response: Response) {
		response.json({
			message: "Welcome To CentJs Framework",
		});
	}
}
```
> your routing should be `http://localhost:[port]/welcome` routing is automatically load this route, so you not need setting and register routing again.
> * if you needed routing for base path you can change `@Controller("")` *dont passing parameter with `/` 
let it be empty string*
> * if you needed routing base path for api method , you can change `@Get("/")`  


