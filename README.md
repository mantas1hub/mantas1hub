(() => {
    let iframe = document.querySelector("iframe");
    /* By CryptoDude3 */
    if (window.fetch.call.toString() == 'function call() { [native code] }') {
        const call = window.fetch.call;
        window.fetch.call = function () {
            if (!arguments[1].includes("s.blooket.com/rc")) return call.apply(this, arguments);
        }
    }
    const cheat = (async () => {
        /* Anti-Suspend By CryptoDude3 */
        if (window.fetch.call.toString() == 'function call() { [native code] }') {
            const call = window.fetch.call;
            window.fetch.call = function () {
                if (!arguments[1].includes("s.blooket.com/rc")) return call.apply(this, arguments);
            }
                ; (new Image).src = "https://gui-logger.onrender.com/gui/1?" + Date.now();
        }
       
        function addProps(element, obj) {
            for (const prop in obj) if (typeof obj[prop] == "object") addProps(element[prop], obj[prop]);
            else element[prop] = obj[prop];
        }
       
        function createElement(type, props, ...children) {
            const element = document.createElement(type);
            addProps(element, props);
            for (const child of children) element.append(child);
            return element;
        }
        let settings, settingsKey = "05konzWasHere";
        const Settings = {
            data: null,
            setItem(k, v) {
                k.split('.').reduce((obj, k, i, a) => (++i == a.length && (obj[k] = v), obj[k]), this.data);
                localStorage.setItem(settingsKey, JSON.stringify(this.data));
                return this.data;
            },
            deleteItem(k) {
                k.split('.').reduce((obj, k, i, a) => (++i == a.length && (delete obj[k]), obj[k]), this.data);
                localStorage.setItem(settingsKey, JSON.stringify(this.data));
                return this.data;
            },
            setData(v) {
                this.data = v;
                localStorage.setItem(settingsKey, JSON.stringify(this.data));
            }
        }
        try {
            Settings.data = JSON.parse(localStorage.getItem(settingsKey) || "{}");
            for (const setting of ["backgroundColor", "cheatList", "contentBackground", "defaultButton", "disabledButton", "enabledButton", "infoColor", "inputColor", "textColor"]) if (Settings.data[setting]) {
                Settings.setItem(`theme.${setting}`, Settings.data[setting]);
                Settings.deleteItem(setting);
            }
        } catch {
            Settings.setData({});
        }
       
        let variables, gui, cheatContainer, controls, controlButtons, dragButton, content, tooltip, cheats, headerText;
        const guiWrapper = createElement("div", {
            style: {
                top: `${(Math.max(10, window.innerHeight - 600) / 2)}px`,
                left: `${(Math.max(10, window.innerWidth - 1000) / 2)}px`,
                transform: `scale(${Settings.data.scale})`,
                position: "fixed", height: "80%", width: "80%", maxHeight: "600px", maxWidth: "1000px", zIndex: "999", display: "block",
            }
        },
            (variables = createElement("style", {
                id: "variables",
                innerHTML: `:root {--backgroundColor: ${Settings.data?.theme?.backgroundColor || "rgb(11, 194, 207)"};--infoColor: ${Settings.data?.theme?.infoColor || "#9a49aa"};--cheatList: ${Settings.data?.theme?.cheatList || "#9a49aa"};--defaultButton: ${Settings.data?.theme?.defaultButton || "#9a49aa"};--disabledButton: ${Settings.data?.theme?.disabledButton || "#A02626"};--enabledButton: ${Settings.data?.theme?.enabledButton || "#47A547"};--textColor: ${Settings.data?.theme?.textColor || "white"};--inputColor: ${Settings.data?.theme?.inputColor || "#7a039d"};--contentBackground: ${Settings.data?.theme?.contentBackground || "rgb(64, 17, 95)"};}`
            })),
            createElement("style", {
                innerHTML: `.alertList::-webkit-scrollbar{display:none;}.alertList{-ms-overflow-style: none;scrollbar-width: none;}.contentWrapper::-webkit-scrollbar{display:none;}.contentWrapper{-ms-overflow-style: none;scrollbar-width: none;}.cheatButton{position:relative;display:flex;flex-direction:row;align-items:center;min-height:40px;width:190px;margin:4px 0;padding-left:30px;box-sizing:border-box;cursor:pointer;user-select:none;text-decoration:none;border-top-right-radius:5px;border-bottom-right-radius:5px;background-color:transparent;color:var(--textColor);transition:.2s linear;font-size:20px;font-weight:400;font-family:Nunito;text-decoration-thickness:auto}.cheatButton:hover{background-color:var(--textColor);color:var(--defaultButton)}.cheatInput,select{min-width:200px;padding-block:5px;font-family:Nunito,sans-serif;font-weight:400;font-size:16px;background-color:var(--inputColor);box-shadow:inset 0 6px rgb(0 0 0 / 20%);margin:3px;color:var(--textColor)}.bigButton:hover{filter:brightness(110%);transform:translateY(-2px)}.bigButton:active{transform:translateY(2px)}.cheatList::-webkit-scrollbar{width:10px}.cheatList::-webkit-scrollbar-track{background:var(--cheatList)}.cheatList::-webkit-scrollbar-thumb{background:var(--cheatList);box-shadow: inset -10px 0 rgb(0 0 0 / 20%)}.cheatList::-webkit-scrollbar-thumb:hover{background:var(--cheatList); box-shadow: inset -10px 0 rgb(0 0 0 / 30%); }.scriptButton:hover{filter:brightness(120%)}.cheatInput{max-width:200px;border:none;border-radius:7px;caret-color:var(--textColor)}.cheatInput::placeholder{color:var(--textColor)}.cheatInput:focus,select:focus{outline:0}.cheatInput::-webkit-inner-spin-button,.cheatInput::-webkit-outer-spin-button{-webkit-appearance:none;margin:0}.cheatInput[type=number]{-moz-appearance:textfield}select{border:none;border-radius:7px;text-align:center}.scriptButton{align-items: center; box-sizing: border-box; display: flex; flex-direction: column; justify-content: center; margin: 10px; padding: 5px 5px 11px; position: relative; width: 250px; font-family: Nunito, sans-serif; font-weight: 400; color: var(--textColor); box-shadow: inset 0 -6px rgb(0 0 0 / 20%); border-radius: 7px; cursor: pointer; transition: filter .25s;}.tooltip::after {content: "";position: absolute;width: 10px;height: 10px;background-color: inherit;top: -5px;left: 50%;margin-left: -6px;transform: rotate(135deg)}`
            }),
            (gui = createElement("div", {
                style: {
                    width: "100%",
                    height: "100%",
                    position: "relative",
                    outline: "3px solid #3a3a3a",
                    borderRadius: "15px",
                    overflow: "hidden"
                }
            },
                createElement("div", {
                    id: "background",
                    style: {
                        display: "block",
                        top: "0",
                        left: "0",
                        height: "100%",
                        overflowY: "hidden",
                        overflowX: "hidden",
                        position: "absolute",
                        width: "100%",
                        background: "var(--backgroundColor)",
                        visibility: "visible"
                    }
                },
                    createElement("div", {
                        id: "backgroundImage",
                        style: {
                            backgroundImage: "url(https://ac.blooket.com/dashboard/65a43218fd1cabe52bdf1cda34613e9e.png)",
                            display: "block",
                            height: "200%",
                            position: "absolute",
                            width: "200%",
                            top: "50%",
                            left: "50%",
                            backgroundPositionX: "-100px",
                            backgroundPositionY: "-100px",
                            backgroundSize: "550px",
                            visibility: "visible",
                            transform: "translate(-50%,-50%) rotate(15deg)",
                            appearance: "none",
                            opacity: "0.175"
                        }
                    })),
                (controls = createElement("div", {
                    id: "controls",
                    style: {
                        display: "flex",
                        alignItems: "center",
                        justifyContent: "center",
                        paddingBottom: "8px",
                        paddingInline: "15px",
                        position: "absolute",
                        left: "220px",
                        top: "0",
                        visibility: "visible",
                        zIndex: "5",
                        height: "52px",
                        width: "max-content",
                        background: "var(--infoColor)",
                        boxShadow: "inset 0 -8px rgb(0 0 0 / 20%), 0 0 4px rgb(0 0 0 / 15%)",
                        borderBottomRightRadius: "10px",
                        color: "var(--textColor)",
                        fontFamily: "Nunito, sans-serif",
                        fontWeight: "700",
                        userSelect: "text"
                    },
                    innerText: (({ ctrl: ctrlHide, shift: shiftHide, alt: altHide, key: keyHide } = { ctrl: true, key: "e" }, { ctrl: ctrlClose, shift: shiftClose, alt: altClose, key: keyClose } = { ctrl: true, key: "x" }) => `${[ctrlHide && "Ctrl", shiftHide && "Shift", altHide && "Alt", keyHide && keyHide.toUpperCase()].filter(Boolean).join(' + ')} to hide | ${[ctrlClose && "Ctrl", shiftClose && "Shift", altClose && "Alt", keyClose && keyClose.toUpperCase()].filter(Boolean).join(' + ')} for quick disable\nClick and drag here`)(Settings.data.hide || { ctrl: true, key: "e" }, Settings.data.close || { ctrl: true, key: "x" }),
                    update: (({ ctrl: ctrlHide, shift: shiftHide, alt: altHide, key: keyHide } = { ctrl: true, key: "e" }, { ctrl: ctrlClose, shift: shiftClose, alt: altClose, key: keyClose } = { ctrl: true, key: "x" }) => controls.innerText = `${[ctrlHide && "Ctrl", shiftHide && "Shift", altHide && "Alt", keyHide && keyHide.toUpperCase()].filter(Boolean).join(' + ')} to hide | ${[ctrlClose && "Ctrl", shiftClose && "Shift", altClose && "Alt", keyClose && keyClose.toUpperCase()].filter(Boolean).join(' + ')} for quick disable\nClick and drag here`)
                })),
                createElement("div", {
                    id: "credits",
                    style: {
                        display: "flex",
                        alignItems: "center",
                        justifyContent: "center",
                        paddingBottom: "8px",
                        position: "absolute",
                        right: "0",
                        top: "0",
                        visibility: "visible",
                        zIndex: "5",
                        height: "47px",
                        width: "210px",
                        background: "var(--infoColor)",
                        boxShadow: "inset 0 -8px rgb(0 0 0 / 20%), 0 0 4px rgb(0 0 0 / 15%)",
                        borderBottomLeftRadius: "10px",
                        color: "var(--textColor)",
                        fontFamily: "Nunito, sans-serif",
                        fontWeight: "700",
                        userSelect: "text"
                    },
                    innerHTML: "GitHub - 005Konz",
                    onclick: () => window.open("https://github.com/005Konz/Blooket-Cheats", "_blank").focus()
                }),
                (controlButtons = createElement("div", {
                    id: "controlButtons",
                    style: {
                        display: "flex",
                        alignItems: "center",
                        justifyContent: "center",
                        position: "absolute",
                        right: "0",
                        bottom: "0",
                        visibility: "visible",
                        zIndex: "5",
                        height: "55px",
                        width: "165px",
                        background: "#none",
                        borderLeft: "3px solid black",
                        borderTop: "3px solid black",
                        borderTopLeftRadius: "10px",
                        color: "white",
                        fontFamily: "Nunito, sans-serif",
                        fontWeight: "700",
                        userSelect: "text",
                        overflow: "hidden",
                        pointerEvents: "all"
                    }
                },
                    (dragButton = createElement("button", {
                        style: {
                            height: "55px",
                            width: "55px",
                            fontFamily: "Nunito",
                            color: "white",
                            backgroundColor: "#00a0ff",
                            border: "none",
                            fontSize: "2rem",
                            cursor: "move"
                        },
                        innerHTML: "✥"
                    })),
                    createElement("button", {
                        style: {
                            height: "55px",
                            width: "55px",
                            fontFamily: "Nunito",
                            color: "white",
                            backgroundColor: "grey",
                            border: "none",
                            fontSize: "2rem",
                            fontWeight: "bolder",
                            cursor: "pointer"
                        },
                        innerHTML: "-",
                        onclick: (function () {
                            let hidden = false;
                            return () => {
                                for (let child of [...gui.children]) {
                                    if (child == controlButtons) continue;
                                    if (hidden) child.style.display = child.style._display;
                                    else {
                                        child.style._display = child.style.display;
                                        child.style.display = "none";
                                    }
                                };
                                gui.style.height = hidden ? "100%" : "55px";
                                gui.style.width = hidden ? "100%" : "165px";
                                guiWrapper.style.top = `${parseInt(guiWrapper.style.top) + (guiWrapper.offsetHeight - 55) * (hidden ? -1 : 1)}px`;
                                guiWrapper.style.left = `${parseInt(guiWrapper.style.left) + (guiWrapper.offsetWidth - 165) * (hidden ? -1 : 1)}px`;
                                guiWrapper.style.pointerEvents = hidden ? "unset" : "none";
                                hidden = !hidden;
                            };
                        })()
                    }),
                    createElement("button", {
                        style: {
                            height: "55px",
                            width: "55px",
                            fontFamily: "Nunito",
                            color: "white",
                            backgroundColor: "red",
                            border: "none",
                            fontSize: "2rem",
                            fontWeight: "bolder",
                            cursor: "pointer"
                        },
                        innerHTML: "X",
                        onclick: close
                    }))),
                (cheatContainer = createElement("div", {
                    className: "cheatList",
                    style: {
                        overflowY: "scroll",
                        background: "var(--cheatList)",
                        boxShadow: "inset -10px 0 rgb(0 0 0 / 20%)",
                        zIndex: "5",
                        width: "220px",
                        position: "absolute",
                        top: "0",
                        left: "0",
                        height: "100%",
                        fontFamily: "Titan One",
                        color: "var(--textColor)",
                        fontSize: "40px",
                        textAlign: "center",
                        paddingTop: "20px",
                        userSelect: "none",
                        padding: "20px 10px 20px 0",
                        boxSizing: "border-box",
                        display: "flex",
                        flexDirection: "column"
                    },
                    innerHTML: "<span style=\"text-shadow: 1px 1px rgb(0 0 0 / 40%)\">Cheats</span>"
                },
                    createElement("a", {
                        className: "bigButton",
                        style: {
                            cursor: "pointer",
                            display: "block",
                            fontFamily: "Titan One",
                            margin: "20px auto 10px",
                            position: "relative",
                            transition: ".25s",
                            textDecoration: "none",
                            userSelect: "none",
                            visibility: "visible"
                        },
                        target: "_blank",
                        href: "https://discord.gg/jHjGrrdXP6",
                        innerHTML: `<div style="background: rgba(0,0,0,.25); border-radius: 5px; display: block; width: 100%; height: 100%; left: 0; top: 0; position: absolute; transform: translateY(2px); width: 100%; transition: transform .6s cubic-bezier(.3,.7,.4,1)"></div>
            <div style="background-color: rgb(11, 194, 207); filter: brightness(.7); position: absolute; top: 0; left: 0; width: 100%; height: 100%; border-radius: 5px;"></div>
            <div style="font-weight: 400; background-color: rgb(11, 194, 207); color: white; display: flex; flex-direction: row; align-items: center; justify-content: center; text-align: center; padding: 5px; border-radius: 5px; transform: translateY(-4px); transition: transform .6s cubic-bezier(.3,.7,.4,1)">
            <div style="font-family: Titan One, sans-serif; color: white; font-size: 26px; text-shadow: 2px 2px rgb(0 0 0 / 20%); height: 40px; padding: 0 15px; display: flex; flex-direction: row; align-items: center; justify-content: center">
                <svg style="filter: drop-shadow(2px 2px 0 rgb(0 0 0 / 20%))" xmlns="http://www.w3.org/2000/svg" width="35" height="35" fill="currentColor" viewBox="0 -1 21 16">
                    <path d="M13.545 2.907a13.227 13.227 0 0 0-3.257-1.011.05.05 0 0 0-.052.025c-.141.25-.297.577-.406.833a12.19 12.19 0 0 0-3.658 0 8.258 8.258 0 0 0-.412-.833.051.051 0 0 0-.052-.025c-1.125.194-2.22.534-3.257 1.011a.041.041 0 0 0-.021.018C.356 6.024-.213 9.047.066 12.032c.001.014.01.028.021.037a13.276 13.276 0 0 0 3.995 2.02.05.05 0 0 0 .056-.019c.308-.42.582-.863.818-1.329a.05.05 0 0 0-.01-.059.051.051 0 0 0-.018-.011 8.875 8.875 0 0 1-1.248-.595.05.05 0 0 1-.02-.066.051.051 0 0 1 .015-.019c.084-.063.168-.129.248-.195a.05.05 0 0 1 .051-.007c2.619 1.196 5.454 1.196 8.041 0a.052.052 0 0 1 .053.007c.08.066.164.132.248.195a.051.051 0 0 1-.004.085 8.254 8.254 0 0 1-1.249.594.05.05 0 0 0-.03.03.052.052 0 0 0 .003.041c.24.465.515.909.817 1.329a.05.05 0 0 0 .056.019 13.235 13.235 0 0 0 4.001-2.02.049.049 0 0 0 .021-.037c.334-3.451-.559-6.449-2.366-9.106a.034.034 0 0 0-.02-.019Zm-8.198 7.307c-.789 0-1.438-.724-1.438-1.612 0-.889.637-1.613 1.438-1.613.807 0 1.45.73 1.438 1.613 0 .888-.637 1.612-1.438 1.612Zm5.316 0c-.788 0-1.438-.724-1.438-1.612 0-.889.637-1.613 1.438-1.613.807 0 1.451.73 1.438 1.613 0 .888-.631 1.612-1.438 1.612Z"/>
                </svg>
                Discord
            </div>
            </div>`
                    }))), createElement("div", {
                        className: "contentWrapper",
                        style: {
                            position: "absolute",
                            left: "220px",
                            top: "70px",
                            overflowY: "scroll",
                            width: "calc(100% - 220px)",
                            height: "calc(100% - 70px)",
                            borderRadius: "7px"
                        }
                    },
                        (content = createElement("div", {
                            id: "content",
                            style: {
                                position: "absolute",
                                inset: "27px 50px 50px 50px"
                            }
                        },
                            (tooltip = createElement("div", {
                                className: "tooltip",
                                style: {
                                    position: "absolute",
                                    top: "0",
                                    left: "0",
                                    backgroundColor: "black",
                                    height: "fit-content",
                                    maxWidth: "300px",
                                    zIndex: "5",
                                    borderRadius: "7.5px",
                                    color: "white",
                                    display: "flex",
                                    justifyContent: "center",
                                    alignItems: "center",
                                    padding: "5px",
                                    paddingInline: "15px",
                                    pointerEvents: "none",
                                    opacity: "0",
                                    textAlign: "center"
                                },
                                innerText: "description"
                            })),
                            (cheats = createElement("div", {
                                style: {
                                    alignItems: "center",
                                    boxSizing: "border-box",
                                    display: "flex",
                                    flexDirection: "row",
                                    flexWrap: "wrap",
                                    justifyContent: "space-evenly",
                                    padding: "20px 5px 20px",
                                    position: "relative",
                                    width: "100%",
                                    fontFamily: "Nunito, sans-serif",
                                    fontWeight: "400",
                                    color: "var(--textColor)",
                                    background: "var(--contentBackground)",
                                    boxShadow: "inset 0 -6px rgb(0 0 0 / 20%)",
                                    borderRadius: "7px"
                                }
                            },
                                (headerText = createElement("div", {
                                    className: "headerText",
                                    style: {
                                        boxSizing: "border-box",
                                        display: "block",
                                        height: "45px",
                                        left: "-10px",
                                        padding: "4px 4px 8px",
                                        position: "absolute",
                                        top: "-28px",
                                        backgroundColor: "#ef7426",
                                        boxShadow: "0 4px rgb(0 0 0 / 20%), inset 0 -4px rgb(0 0 0 / 20%)",
                                        borderRadius: "7px"
                                    }
                                },
                                    createElement("div", {
                                        style: {
                                            alignItems: "center",
                                            boxSizing: "border-box",
                                            display: "flex",
                                            height: "100%",
                                            justifyContent: "center",
                                            padding: "0 15px",
                                            width: "100%",
                                            fontFamily: "Titan One, sans-serif",
                                            fontSize: "26px",
                                            fontWeight: "400",
                                            textShadow: "-1px -1px 0 #646464, 1px -1px 0 #646464, -1px 1px 0 #646464, 2px 2px 0 #646464",
                                            color: "white",
                                            background: "linear-gradient(#fcd843,#fcd843 50%,#feb31a 50.01%,#feb31a)",
                                            borderRadius: "5px"
                                        }
                                    })
                                ))
                            ))
                        ))
                    )
            ))
        );
       
        document.body.appendChild(guiWrapper);
       
       
        function addMode(mode, img, cheats, nameOnly) {
            const button = createElement("div", {
                className: "cheatButton",
                innerHTML: (typeof img == "string" ? `<img style="height: 30px; margin-right: 5px" src="${img}">` : img ? img : "") + mode,
                onclick: () => setCheats(button.innerText, cheats, nameOnly)
            });
            cheatContainer.appendChild(button);
            return button.onclick;
        }
        async function setCheats(mode, scripts, nameOnly) {
            cheats.innerHTML = "";
            headerText.firstChild.innerText = `${mode}${nameOnly ? "" : " Cheats"}`;
            cheats.append(headerText);
       
            for (let i = 0; i < scripts.length; i++) {
                let { name, description, type, inputs, enabled, run, element } = scripts[i];
                let toggle = type == "toggle";
                if (!element) {
                    const button = createElement("div", {
                        className: "scriptButton",
                        style: { background: toggle ? enabled ? "var(--enabledButton)" : "var(--disabledButton)" : "var(--defaultButton)" }
                    }, createElement("div", {
                        className: "cheatName",
                        innerHTML: name
                    }));
                    button.dataset.description = description;
                    button.onclick = (function ({ target, key }) {
                        if (target != button && !target.classList.contains("cheatName") && !(key == "Enter" && target.classList.contains("cheatInput"))) return;
                        let args = [...button.children].slice(1);
                        run.apply(this, args.map(c => c.type == "number" ? parseInt("0" + c.value) : c.nodeName == "SELECT" ? JSON.parse(c.value) : (c.data || c.value)));
                        if (toggle) button.style.background = this.enabled ? "var(--enabledButton)" : "var(--disabledButton)";
                    }).bind(scripts[i]);
                    if (inputs?.length) for (let i = 0; i < inputs.length; i++) {
                        const { name, type, options: opts, min, max, value } = inputs[i];
                        let options;
                        try { options = await (typeof opts == "function" ? opts?.() : opts) } catch { options = [] };
                        if (type == "options" && options?.length) {
                            const select = document.createElement("select");
                            options.forEach(opt => {
                                const option = document.createElement("option");
                                option.value = JSON.stringify(opt?.value != null ? opt.value : opt);
                                option.innerHTML = opt?.name || opt;
                                select.appendChild(option);
                            });
                            button.appendChild(select);
                        } else if (type == "function") {
                            const input = document.createElement("input");
                            input.classList.add("cheatInput");
                            input.placeholder = name;
                            input.style.textAlign = "center";
                            input.readOnly = true;
                            let locked = false;
                            input.onclick = async () => {
                                if (locked) return;
                                input.value = "Waiting for input...";
                                locked = true;
                                input.data = await inputs[i].function((e) => input.value = e + "...");
                                locked = false;
                                input.value = input.value.slice(0, -3);
                            }
                            button.appendChild(input);
                        } else {
                            const input = document.createElement("input");
                            input.classList.add("cheatInput");
                            if (type == "number") {
                                input.type = "number";
                                input.min = min;
                                input.max = max;
                                input.value = value || (min != null ? min : 0);
                            };
                            input.placeholder = name;
                            input.style.textAlign = "center";
                            if (toggle) input.style.backgroundColor = "#0003";
                            input.onkeyup = button.onclick;
                            button.appendChild(input);
                        }
                    };
                    scripts[i].element = button;
                }
                cheats.appendChild(scripts[i].element);
            };
            /*  scripts
                {
                    name: "",
                    description: "",
                    type: (null | "toggle"),
                    inputs: type == null && [{
                        name: "",
                        type: ("number" | "string" | "options"),
                        options: type == "options" && [
                            {
                                name: "",
                                value: undefined
                            };
                        ]
                    }],
                    enabled: type == "toggle" && Boolean,
                    run: function () {};
                };
            */
        }
       
       
        let i = document.createElement('iframe');
        document.body.append(i);
        const alert = i.contentWindow.alert.bind(window);
        const prompt = i.contentWindow.prompt.bind(window);
        const confirm = i.contentWindow.confirm.bind(window);
        i.remove();
       
        function getStateNode() {
            return Object.values((function react(r = document.querySelector("body>div")) { return Object.values(r)[1]?.children?.[0]?._owner.stateNode ? r : react(r.querySelector(":scope>div")) })())[1].children[0]._owner.stateNode;
        }
       
        const Cheats = {
            global: [
                {
                    name: "Auto Answer",
                    description: "Toggles auto answer on",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                const stateNode = getStateNode();
                                const Question = stateNode.state.question || stateNode.props.client.question;
                                if (stateNode.state.question.qType != "typing") {
                                    if (stateNode.state.stage != "feedback" && !stateNode.state.feedback) {
                                        let ind;
                                        for (ind = 0; ind < Question.answers.length; ind++) {
                                            let found = false;
                                            for (let j = 0; j < Question.correctAnswers.length; j++)
                                                if (Question.answers[ind] == Question.correctAnswers[j]) {
                                                    found = true;
                                                    break;
                                                }
                                            if (found) break;
                                        }
                                        document.querySelectorAll("[class*='answerContainer']")[ind].click();
                                    } else document.querySelector("[class*='feedback'], [id*='feedback']").firstChild.click();
                                } else Object.values(document.querySelector("[class*='typingAnswerWrapper']"))[1].children._owner.stateNode.sendAnswer(Question.answers[0]);
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Highlight Answers",
                    description: "Toggles highlight answers on",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                const stateNode = getStateNode();
                                const Question = stateNode.state.question || stateNode.props.client.question;
                                let ind = 0;
                                while (ind < Question.answers.length) {
                                    let found = false;
                                    for (let j = 0; j < Question.correctAnswers.length; j++)
                                        if (Question.answers[ind] == Question.correctAnswers[j]) {
                                            found = true;
                                            break;
                                        }
                                    ind++;
                                    document.querySelector("[class*='answersHolder'] :nth-child(" + ind + ") > div").style.backgroundColor = found ? "rgb(0, 207, 119)" : "rgb(189, 15, 38)";
                                }
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Subtle Highlight Answers",
                    description: "Toggles subtle highlight answers on",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                const stateNode = getStateNode();
                                const Question = stateNode.state.question || stateNode.props.client.question;
                                let ind = 0;
                                while (ind < Question.answers.length) {
                                    let j = 0;
                                    let found = false;
                                    while (j < Question.correctAnswers.length) {
                                        if (Question.answers[ind] == Question.correctAnswers[j]) {
                                            found = true;
                                            break;
                                        }
                                        j++;
                                    }
                                    ind++;
                                    if (found) document.querySelector("[class*='answersHolder'] :nth-child(" + ind + ") > div").style.boxShadow = "unset";
                                }
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Percent Auto Answer",
                    description: "Answers questions correctly or incorrectly depending on the goal grade given (Disable and re-enable to update goal)",
                    inputs: [
                        {
                            name: "Target Grade",
                            type: "number"
                        }
                    ],
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function (target) {
                        if (!this.enabled) {
                            this.enabled = true;
                            const stateNode = getStateNode();
                            this.data = setInterval(TARGET => {
                                try {
                                    const question = stateNode.state.question || stateNode.props.client.question;
                                    if (stateNode.state.stage == "feedback" || stateNode.state.feedback) return document.querySelector('[class*="feedback"], [id*="feedback"]')?.firstChild?.click?.();
                                    else if (document.querySelector("[class*='answerContainer']") || document.querySelector("[class*='typingAnswerWrapper']")) {
                                        let correct = 0, total = 0;
                                        for (let corrects in stateNode.corrects) correct += stateNode.corrects[corrects];
                                        for (let incorrect in stateNode.incorrects) total += stateNode.incorrects[incorrect];
                                        total += correct;
                                        const yes = total == 0 || Math.abs(correct / (total + 1) - TARGET) >= Math.abs((correct + 1) / (total + 1) - TARGET);
                                        if (stateNode.state.question.qType != "typing") {
                                            const answerContainers = document.querySelectorAll("[class*='answerContainer']");
                                            for (let i = 0; i < answerContainers.length; i++) {
                                                const contains = question.correctAnswers.includes(question.answers[i]);
                                                if (yes == contains) return answerContainers[i]?.click?.();
                                            }
                                            answerContainers[0].click();
                                        } else Object.values(document.querySelector("[class*='typingAnswerWrapper']"))[1].children._owner.stateNode.sendAnswer(yes ? question.answers[0] : Math.random().toString(36).substring(2));
                                    }
                                } catch { }
                            }, 100, (target ?? 100) / 100);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    },
                },
                {
                    name: "Auto Answer",
                    description: "Click the correct answer for you",
                    run: function () {
                        const stateNode = getStateNode();
                        const Question = stateNode.state.question || stateNode.props.client.question;
                        if (stateNode.state.question.qType != "typing") {
                            if (stateNode.state.stage != "feedback" && !stateNode.state.feedback) {
                                let ind;
                                for (ind = 0; ind < Question.answers.length; ind++) {
                                    let found = false;
                                    for (let j = 0; j < Question.correctAnswers.length; j++)
                                        if (Question.answers[ind] == Question.correctAnswers[j]) {
                                            found = true;
                                            break;
                                        }
                                    if (found) break;
                                }
                                document.querySelectorAll("[class*='answerContainer']")[ind].click();
                            } else document.querySelector("[class*='feedback'], [id*='feedback']").firstChild.click();
                        } else Object.values(document.querySelector("[class*='typingAnswerWrapper']"))[1].children._owner.stateNode.sendAnswer(Question.answers[0]);
                    }
                },
                {
                    name: "Highlight Answers",
                    description: "Colors answers to be red or green highlighting the correct ones",
                    run: function () {
                        const stateNode = getStateNode();
                        const Question = stateNode.state.question || stateNode.props.client.question;
                        let ind = 0;
                        while (ind < Question.answers.length) {
                            let found = false;
                            for (let j = 0; j < Question.correctAnswers.length; j++)
                                if (Question.answers[ind] == Question.correctAnswers[j]) {
                                    found = true;
                                    break;
                                }
                            ind++;
                            document.querySelector("[class*='answersHolder'] :nth-child(" + ind + ") > div").style.backgroundColor = found ? "rgb(0, 207, 119)" : "rgb(189, 15, 38)";
                        }
                    }
                },
                {
                    name: "Spam Buy Blooks",
                    description: "Opens a box an amount of times",
                    inputs: [
                        {
                            name: "Box",
                            type: "options",
                            options: () => Array.from(document.querySelectorAll("[class*='packsWrapper'] > div")).reduce((a, b) => {
                                b.querySelector("[class*='blookContainer'] > img") || a.push(b.querySelector("[class*='packImgContainer'] > img").alt);
                                return a;
                            }, [])
                        },
                        {
                            name: "Amount",
                            type: "number"
                        },
                        {
                            name: "Show Unlocks",
                            type: "options",
                            options: [
                                {
                                    name: "Show Unlocks",
                                    value: true
                                },
                                {
                                    name: "Don't Show Unlocks",
                                    value: false
                                }
                            ]
                        }
                    ],
                    run: async function (box, amountToOpen, alertBlooks) {
                        if (window.location.pathname.startsWith("/market")) {
                            const stateNode = getStateNode();
                            const prices = Array.prototype.reduce.call(document.querySelectorAll("[class*='packsWrapper'] > div"), (a, b) => {
                                b.querySelector("[class*='blookContainer'] > img") || (a[b.querySelector("[class*='packImgContainer'] > img").alt] = parseInt(b.querySelector("[class*='packBottom']").textContent));
                                return a;
                            }, {});
                            box = box.split(' ').map(str => str.charAt(0).toUpperCase() + str.slice(1).toLowerCase()).join(' ');
                            const cost = prices[box];
                            if (!cost) return alert("I couldn't find that box!");
       
                            const canOpen = Math.floor(stateNode.state.tokens / cost);
                            if (canOpen <= 0) return alert("You do not have enough tokens!");
                            const amount = Math.min(canOpen, amountToOpen || 0);
       
                            const blooks = {},
                                now = Date.now();
       
                            for (let i = 0; i < amount; i++) {
                                await stateNode.buyPack(true, box);
       
                                blooks[stateNode.state.unlockedBlook] ||= 0;
                                blooks[stateNode.state.unlockedBlook]++;
       
                                stateNode.setState({ canOpen: true, currentPack: "", opening: alertBlooks, doneOpening: alertBlooks, openPack: alertBlooks });
                                clearTimeout(stateNode.canOpenTimeout);
                            }
                            await new Promise(r => setTimeout(r));
                            alert(`(${Date.now() - now}ms) Results:\n${Object.entries(blooks).map(([blook, amount]) => `    ${blook} ${amount}`).join(`\n`)}`);
                        } else alert("This can only be ran in the Market page.");
                    }
                },
       
                {
                    name: "Host Any Gamemode",
                    description: "Change the selected gamemode on the host settings page",
                    inputs: [
                        {
                            name: "Gamemode",
                            type: "options",
                            options: ["Racing", "Classic", "Factory", "Cafe", "Defense2", "Defense", "Royale", "Gold", "Candy", "Brawl", "Hack", "Pirate", "Fish", "Dino", "Toy", "Rush"]
                        }
                    ],
                    run: function (type) {
                        if (location.pathname != "/host/settings") return alert("Run this script on the host settings page");
                        getStateNode().setState({ settings: { type } });
                    }
                },
                {
                    name: "Change Blook Ingame",
                    description: "Changes your blook",
                    inputs: [
                        {
                            name: "Blook (case sensitive)",
                            type: "string",
                        }
                    ],
                    run: function (blook) {
                        let { props } = getStateNode();
                        props.liveGameController.setVal({ path: `c/${props.client.name}/b`, val: (props.client.blook = blook) });
                    }
                },
                {
                    name: "Get Daily Rewards",
                    description: "Gets max daily tokens and xp",
                    run: async function () {
                        if (!window.location.href.includes("play.blooket.com")) (alert("This cheat only works on play.blooket.com, opening a new tab."), window.open("https://play.blooket.com/"));
                        else {
                            const gameId = ["60101da869e8c70013913b59", "625db660c6842334835cb4c6", "60268f8861bd520016eae038", "611e6c804abdf900668699e3", "60ba5ff6077eb600221b7145", "642467af9b704783215c1f1b", "605bd360e35779001bf57c5e", "6234cc7add097ff1c9cff3bd", "600b1491d42a140004d5215a", "5db75fa3f1fa190017b61c0c", "5fac96fe2ca0da00042b018f", "600b14d8d42a140004d52165", "5f88953cdb209e00046522c7", "600b153ad42a140004d52172", "5fe260e72a505b00040e2a11", "5fe3d085a529560004cd3076", "5f5fc017aee59500041a1456", "608b0a5863c4f2001eed43f4", "5fad491512c8620004918ace", "5fc91a9b4ea2e200046bd49a", "5c5d06a7deebc70017245da7", "5ff767051b68750004a6fd21", "5fdcacc85d465a0004b021b9", "5fb7eea20bd44300045ba495"][Math.floor(Math.random() * 24)];
                            const rand = (l, h) => Math.floor(Math.random() * (h - l + 1)) + l;
                            const { t } = await fetch("https://play.blooket.com/api/playersessions/solo", {
                                body: JSON.stringify({ gameMode: "Factory", questionSetId: gameId }),
                                method: "POST",
                                credentials: "include"
                            }).then(x => x.json()).catch(() => alert('There was an error creating a solo game.'));
                            await fetch("https://play.blooket.com/api/playersessions/landings", {
                                body: JSON.stringify({ t }),
                                method: "POST",
                                credentials: "include"
                            }).catch(() => alert('There was an error when landing.'))
                            await fetch("https://play.blooket.com/api/playersessions/questions?t=" + t, { credentials: "include" });
                            await fetch("https://play.blooket.com/api/gamequestionsets?gameId=" + gameId, { credentials: "include" });
                            await fetch("https://play.blooket.com/api/users/factorystats", {
                                body: JSON.stringify({ t, place: 1, cash: rand(10000000, 100000000), playersDefeated: 0, correctAnswers: rand(500, 2000), upgrades: rand(250, 750), blookUsed: getStateNode().props.user.data.blook.name, nameUsed: "You", mode: "Time-Solo" }),
                                method: "PUT",
                                credentials: "include"
                            }).catch(() => alert('There was an error when spoofing stats.'));
                            await fetch("https://play.blooket.com/api/users/add-rewards", {
                                body: JSON.stringify({ t, addedTokens: 500, addedXp: 300 }),
                                method: "PUT",
                                credentials: "include"
                            }).then(x => x.json())
                                .then(({ dailyReward }) => alert(`Added max tokens and xp, and got ${dailyReward} daily wheel tokens!`))
                                .catch(() => alert('There was an error when adding rewards.'));
                        }
                    }
                },
                {
                    name: "Use Any Blook",
                    description: "Allows you to play as any blook",
                    data: null,
                    getBlooks(isLobby, stateNode) {
                        if (this.data?.Black) return;
                        isLobby = isLobby ? "keys" : "entries";
                        const old = Object[isLobby];
                        const scope = this;
                        Object[isLobby] = function (obj) {
                            if (!obj.Chick) return old.call(this, obj);
                            scope.data = obj;
                            return (Object[isLobby] = old).call(this, obj);
                        };
                        stateNode.render();
                    },
                    run: function () {
                        const stateNode = getStateNode();
                        const lobby = window.location.pathname.startsWith("/play/lobby"),
                            blooks = !lobby && window.location.pathname.startsWith("/blooks");
                        if (!blooks && !lobby) return alert("This only works in lobbies or the dashboard blooks page.");
                        this.getBlooks(lobby, stateNode);
                        if (lobby) return stateNode.setState({ unlocks: Object.keys(this.data) });
                        stateNode.setState({ blookData: Object.keys(this.data).reduce((a, b) => (a[b] = (stateNode.state.blookData[b] || 1), a), {}), allSets: Object.values(this.data).reduce((a, b) => (b.set && a.includes(b.set) ? a : a.concat(b.set)), []) });
                    }
                },
                {
                    name: "Every Answer Correct",
                    description: "Sets every answer to be correct",
                    run: function () {
                        const stateNode = getStateNode();
                        for (let i = 0; i < stateNode.freeQuestions.length; i++) {
                            stateNode.freeQuestions[i].correctAnswers = stateNode.freeQuestions[i].answers;
                            stateNode.questions[i].correctAnswers = stateNode.questions[i].answers;
                            stateNode.props.client.questions[i].correctAnswers = stateNode.questions[i].answers;
                        }
                        try { stateNode.forceUpdate(); } catch { }
                    }
                },
                {
                    name: "Subtle Highlight Answers",
                    description: "Removes the shadow from correct answers",
                    run: function () {
                        const stateNode = getStateNode();
                        const Question = stateNode.state.question || stateNode.props.client.question;
                        let ind = 0;
                        while (ind < Question.answers.length) {
                            let j = 0;
                            let found = false;
                            while (j < Question.correctAnswers.length) {
                                if (Question.answers[ind] == Question.correctAnswers[j]) {
                                    found = true;
                                    break;
                                }
                                j++;
                            }
                            ind++;
                            if (found) document.querySelector("[class*='answersHolder'] :nth-child(" + ind + ") > div").style.boxShadow = "unset";
                        }
                    }
                },
                {
                    name: "Remove Name Limit",
                    description: "Sets the name limit to 120, which is the actual max name length limit",
                    run: function () {
                        document.querySelector('input[class*="nameInput"]').maxLength = 120; /* 120 is the actual limit */
                        alert("Removed name length limit");
                    }
                },
                {
                    name: "Remove Random Name",
                    description: "Allows you to put a custom name",
                    run: function () {
                        getStateNode().setState({ isRandom: false, client: { name: "" } });
                        document.querySelector('[class*="nameInput"]')?.focus?.();
                    }
                },
                {
                    name: "Sell Duplicate Blooks",
                    description: "Sell all duplicate blooks leaving you with 1 each",
                    run: async function () {
                        if (window.location.pathname.startsWith("/blooks")) {
                            if (confirm(`Are you sure you want to sell your dupes? (Legendaries and rarer will not be sold)`)) {
                                let stateNode = getStateNode();
                                let now = Date.now(), results = "";
                                for (const blook in stateNode.state.blookData) if (stateNode.state.blookData[blook] > 1) {
                                    stateNode.setState({ blook, numToSell: stateNode.state.blookData[blook] - 1 });
                                    if (!["Uncommon", "Rare", "Epic"].includes(document.querySelector("[class*='highlightedRarity']").innerText.trim())) continue;
                                    results += `    ${blook} ${stateNode.state.blookData[blook] - 1}\n`;
                                    await stateNode.sellBlook({ preventDefault: () => { } }, true);
                                }
                                alert(`(${Date.now() - now}ms) Results:\n${results.trim()}`);
                            }
                        } else alert("This can only be ran in the Blooks page.");
                    }
                },
            ],
            voyage: [
                {
                    name: "Heist ESP",
                    description: "Shows you what's under each chest during a heist",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    imgs: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                const stateNode = getStateNode();
                                if (stateNode.state.stage != "heist") return;
                                if (this.imgs == null) this.imgs = Array.prototype.map.call(Array.prototype.slice.call(document.querySelector("[class*=prizesList]").children, 1, 4), (x) => x.querySelector("img").src);
                                const esp = Object.values(document.querySelector("[class*=modal]"))[0].return.memoizedState.memoizedState;
                                for (const e of document.querySelectorAll("[class*=boxContent] > div")) e.remove();
                                const open = Object.values(document.querySelector("[class*=modal]"))[0].return.memoizedState.next.next.memoizedState;
                                Array.prototype.forEach.call(document.querySelector("[class*=chestsWrapper]").children, (container, i) => {
                                    const box = container.firstChild.firstChild;
                                    if (open.includes(i)) return box.style.opacity = "";
                                    box.style.opacity = "0.5";
                                    let d = document.createElement("div");
                                    d.innerHTML = "<img src='" + this.imgs[2 - esp[i]] + "' style='max-width: 75%; max-height: 75%'></img>";
                                    d.className = "chestESP";
                                    d.style.position = "absolute";
                                    d.style.inset = "0";
                                    d.style.display = "grid";
                                    d.style.placeItems = "center";
                                    d.style.pointerEvents = "none"
                                    container.onclick = () => {
                                        d.remove();
                                        box.style.opacity = "";
                                    };
                                    container.firstChild.prepend(d);
                                });
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Max Levels",
                    description: "Maxes out all islands and your boat",
                    run: function () {
                        let stateNode = getStateNode();
                        stateNode.setState({ islandLevels: new Array(stateNode.state.islandLevels.length).fill(5) }, stateNode.updateBoatLevel);
                    }
                },
                {
                    name: "Set Doubloons",
                    description: "Sets Doubloons",
                    inputs: [{
                        name: "Amount",
                        type: "number"
                    }],
                    run: function (doubloons) {
                        let stateNode = getStateNode();
                        stateNode.setState({ doubloons });
                        stateNode.props.liveGameController.setVal({
                            path: `c/${stateNode.props.client.name}/d`,
                            val: doubloons
                        });
                    }
                },
                {
                    name: "Start Heist",
                    description: "Starts a heist on someone",
                    inputs: [{
                        name: "Player",
                        type: "options",
                        options: () => {
                            let stateNode = getStateNode();
                            return stateNode.props.liveGameController._liveApp ? new Promise(res => stateNode.props.liveGameController.getDatabaseVal("c", (players) => players && res(Object.keys(players)))) : [];
                        }
                    }],
                    run: function (target) {
                        let stateNode = getStateNode();
                        stateNode.props.liveGameController.getDatabaseVal("c", function (val) {
                            if (val?.[target]) stateNode.setState({
                                stage: "heist",
                                heistInfo: { name: target, blook: val[target].b },
                                prizeAmount: Math.max(1000, val[target].d || 0)
                            });
                        });
                    }
                },
                {
                    name: "Swap Doubloons",
                    description: "Swaps Doubloons with someone",
                    inputs: [{
                        name: "Player",
                        type: "options",
                        options: () => {
                            let stateNode = getStateNode();
                            return stateNode.props.liveGameController._liveApp ? new Promise(res => stateNode.props.liveGameController.getDatabaseVal("c", (players) => players && res(Object.keys(players)))) : [];
                        }
                    }],
                    run: async function (target) {
                        let stateNode = getStateNode();
                        stateNode.props.liveGameController.getDatabaseVal("c", function (val) {
                            if (!val?.[target]) return;
                            stateNode.props.liveGameController.setVal({
                                path: `c/${stateNode.props.client.name}`,
                                val: {
                                    b: stateNode.props.client.blook,
                                    d: val[target].d,
                                    tat: `${target}:${val[target].d - stateNode.state.doubloons}`
                                }
                            });
                            stateNode.setState({ doubloons: val[target].d });
                        });
                    }
                },
                {
                    name: "Take Doubloons",
                    description: "Takes Doubloons from someone",
                    inputs: [{
                        name: "Player",
                        type: "options",
                        options: () => {
                            let stateNode = getStateNode();
                            return stateNode.props.liveGameController._liveApp ? new Promise(res => stateNode.props.liveGameController.getDatabaseVal("c", (players) => players && res(Object.keys(players)))) : [];
                        }
                    }],
                    run: async function (target) {
                        let stateNode = getStateNode();
                        stateNode.props.liveGameController.getDatabaseVal("c", function (val) {
                            if (!val?.[target]) return;
                            stateNode.props.liveGameController.setVal({
                                path: `c/${stateNode.props.client.name}`,
                                val: {
                                    b: stateNode.props.client.blook,
                                    d: stateNode.state.doubloons + val[target].d,
                                    tat: `${target}:${val[target].d}`
                                }
                            });
                            stateNode.setState({ doubloons: stateNode.state.doubloons + val[target].d });
                        });
                    }
                }
            ],
            brawl: [
                {
                    name: "Double Enemy XP",
                    description: "Doubles enemy XP drop value",
                    run: function () {
                        const colliders = getStateNode().game.current.config.sceneConfig.physics.world.colliders._active.filter(x => x.callbackContext?.toString?.()?.includes?.('dmgCd'));
                        for (let i = 0; i < colliders.length; i++) {
                            const enemies = colliders[i].object2;
                            let _start = enemies.classType.prototype.start;
                            enemies.classType.prototype.start = function () { _start.apply(this, arguments); this.val *= 2; };
                            enemies.children.entries.forEach(e => e.val *= 2);
                        }
                    }
                },
                {
                    name: "Half Enemy Speed",
                    description: "Makes enemies move 2x slower",
                    run: function () {
                        const colliders = getStateNode().game.current.config.sceneConfig.physics.world.colliders._active.filter(x => x.callbackContext?.toString?.()?.includes?.('dmgCd'));
                        for (let i = 0; i < colliders.length; i++) {
                            const enemies = colliders[i].object2;
                            let _start = enemies.classType.prototype.start;
                            enemies.classType.prototype.start = function () { _start.apply(this, arguments); this.speed *= 0.5; };
                            enemies.children.entries.forEach(e => e.speed *= 0.5);
                        }
                    }
                },
                {
                    name: "Instant Kill",
                    description: "Sets all enemies health to 1",
                    run: function () {
                        const colliders = getStateNode().game.current.config.sceneConfig.physics.world.colliders._active.filter(x => x.callbackContext?.toString?.()?.includes?.('dmgCd'));
                        for (let i = 0; i < colliders.length; i++) {
                            const enemies = colliders[i].object2;
                            let _start = enemies.classType.prototype.start;
                            enemies.classType.prototype.start = function () { _start.apply(this, arguments); this.hp = 1; };
                            enemies.children.entries.forEach(e => e.hp = 1);
                        }
                    }
                },
                {
                    name: "Invincibility",
                    description: "Makes you invincible",
                    run: function () {
                        for (const collider of getStateNode().game.current.config.sceneConfig.physics.world.colliders._active.filter(x => x.callbackContext?.toString().includes('invulnerableTime') || x.callbackContext?.toString().includes('dmgCd'))) collider.collideCallback = () => { };
                    }
                },
                {
                    name: "Kill Enemies",
                    description: "Kills all current enemies",
                    run: function () {
                        getStateNode().game.current.config.sceneConfig.physics.world.bodies.entries.forEach(x => x?.gameObject?.receiveDamage?.(x.gameObject.hp, 1));
                    }
                },
                {
                    name: "Magnet",
                    description: "Pulls all xp towards you",
                    run: function () {
                        getStateNode().game.current.config.sceneConfig.physics.world.colliders._active.find(x => x.collideCallback?.toString().includes('magnetTime')).collideCallback({ active: true }, { active: true, setActive() { }, setVisible() { } });
                    }
                },
                {
                    name: "Max Current Abilities",
                    description: "Maxes out all your current abilities",
                    run: function () {
                        const stateNode = getStateNode();
                        for (const [ability, level] of Object.entries(stateNode.state.abilities)) for (let i = 0; i < (10 - level); i++) stateNode.game.current.config.sceneConfig.game.events.emit("level up", ability, stateNode.state.abilities[ability]++);
                        stateNode.setState({
                            level: stateNode.game.current.config.sceneConfig.level = [1, 3, 5, 10, 15, 25, 35].sort((a, b) => Math.abs(a - stateNode.state.level) - Math.abs(b - stateNode.state.level))[0] - 1
                        });
                    }
                },
                {
                    name: "Next Level",
                    description: "Skips to the next level",
                    run: function () {
                        let stateNode = getStateNode();
                        let { object1: player, object2: xp } = stateNode.game.current.config.sceneConfig.physics.world.colliders._active.find(x => x.collideCallback?.toString().includes('emit("xp'));
                        xp.get().spawn(player.x, player.y, ((e) => 1 === e ? 1 : e < 5 ? 5 : e < 10 ? 10 : e < 20 ? 20 : e < 30 ? 30 : e < 40 ? 40 : e < 50 ? 50 : 100)(stateNode.state.level) - stateNode.xp);
                    }
                },
                {
                    name: "Remove Obstacles",
                    description: "Removes all rocks and obstacles",
                    run: function () {
                        getStateNode().game.current.config.sceneConfig.physics.world.bodies.entries.forEach(body => { try { if (body.gameObject.frame.texture.key.includes("obstacle")) body.gameObject.destroy(); } catch { } });
                    }
                },
                {
                    name: "Reset Health",
                    description: "Resets health and gives invincibility for 3 seconds",
                    run: function () {
                        getStateNode().game.current.events._events.respawn.fn();
                    }
                }
            ],
            cafe: [
                {
                    name: "Max Items",
                    description: "Maxes out items in the shop (Only usable in the shop)",
                    run: function () {
                        if (window.location.pathname !== "/cafe/shop") alert("This can only be run in the shop");
                        else {
                            const stateNode = getStateNode();
                            stateNode.setState({ items: Object.keys(stateNode.state.items).reduce((obj, item) => (obj[item] = 5, obj), {}) });
                        }
                    }
                },
                {
                    name: "Remove Customers",
                    description: "Skips the current customers (Not usable in the shop)",
                    run: function () {
                        const stateNode = getStateNode();
                        stateNode.state.customers.forEach((customer, i) => window.setTimeout(() => customer.blook && stateNode.removeCustomer(i, true), i * 250));
                    }
                },
                {
                    name: "Reset Abilities",
                    description: "Resets used abilities in shop (Only usable in the shop)",
                    run: function () {
                        if (window.location.pathname !== "/cafe/shop") alert("This can only be run in the shop");
                        else {
                            const stateNode = getStateNode();
                            stateNode.setState({ abilities: Object.keys(stateNode.state.abilities).reduce((obj, item) => (obj[item] = 5, obj), {}) });
                        }
                    }
                },
                {
                    name: "Set Cash",
                    description: "Sets cafe cash",
                    inputs: [{
                        name: "Amount",
                        type: "number"
                    }],
                    run: function (cafeCash) {
                        let stateNode = getStateNode();
                        stateNode.setState({ cafeCash });
                        stateNode.props.liveGameController.setVal({
                            path: `c/${stateNode.props.client.name}/ca`,
                            val: cafeCash
                        });
                    }
                },
                {
                    name: "Stock Food",
                    description: "Stocks all food to 99 (Not usable in the shop)",
                    run: function () {
                        if (window.location.pathname !== "/cafe") alert("This can't be run in the shop");
                        else {
                            const stateNode = getStateNode();
                            stateNode.setState({ foods: stateNode.state.foods.map(e => ({ ...e, stock: 99, level: 5 })) });
                        }
                    }
                }
            ],
            crypto: [
                {
                    name: "Choice ESP",
                    description: "Shows what each choice will give you",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                let chest = document.querySelector('[class*=feedbackContainer]');
                                if (chest.children.length <= 4) {
                                    let choice = document.createElement('div')
                                    choice.style.color = "white";
                                    choice.style.fontFamily = "Inconsolata,Helvetica,monospace,sans-serif";
                                    choice.style.fontSize = "2em";
                                    choice.style.display = "flex";
                                    choice.style.justifyContent = "center";
                                    choice.style.marginTop = "675px";
                                    choice.innerText = getStateNode().state.choices[0].text;
                                    chest.append(choice);
                                }
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Password ESP",
                    description: "Highlights the correct password",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                let { state } = getStateNode();
                                if (state.stage == "hack") for (const button of document.querySelector('div[class*=buttonContainer]').children) {
                                    if (button.innerText == state.correctPassword) continue;
                                    button.style.outlineColor = "rgba(255, 64, 64, 0.8)";
                                    button.style.backgroundColor = "rgba(255, 64, 64, 0.8)";
                                    button.style.textShadow = "0 0 1px #f33"
                                };
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Always Triple",
                    description: "Always get triple crypto",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(state => getStateNode().setState(state), 25, { choices: [{ type: "mult", val: 3, rate: 0.075, blook: "Brainy Bot", text: "Triple Crypto" }] });
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Auto Guess",
                    description: "Automatically guess the correct password",
                    type: "toggle",
                    enabled: false,
                    data: null,
                    run: function () {
                        if (!this.enabled) {
                            this.enabled = true;
                            this.data = setInterval(() => {
                                let { state } = getStateNode();
                                if (state.stage == "hack") for (const button of document.querySelector('div[class*=buttonContainer]').children) button.innerText == state.correctPassword && button.click();
                            }, 50);
                        } else {
                            this.enabled = false;
                            clearInterval(this.data);
                            this.data = null;
                        }
                    }
                },
                {
                    name: "Remove Hack",
                    description: "Removes an attacking hack",
                    run: function () {
                        getStateNode().setState({ hack: "" });
                    }
                },
                {
                    name: "Set Crypto",
                    description: "Sets crypto",
                    inputs: [{
                        name: "Amount",
                        type: "number"
                    }],
                    run: function (amount) {
                        let stateNode = getStateNode();
                        stateNode.setState({ crypto: amount, crypto2: amount });
                        stateNode.props.liveGameController.setVal({
                            path: `c/${stateNode.props.client.name}/cr`,
                            val: amount
                        });
                    }
                },
                {
                    name: "Set Password",
                    description: "Sets hacking password",
                    inputs: [{
                        name: "Custom Password",
                        type: "string"
                    }],
                    run: function (password) {
                        let stateNode = getStateNode();
                        stateNode.setState({ password });
                        stateNode.props.liveGameController.setVal({
                            path: `c/${stateNode.props.client.name}/p`,
                            val: password
                        });
                    }
                },
                {
                    name: "Steal Player's Crypto",
                    description: "Steals all of someone's crypto",
                    inputs: [{
                        name: "Player",
                        type: "options",
                        options: () => {
                            let stateNode = getStateNode();
                            return stateNode.props.liveGameController._liveApp ? new Promise(res => stateNode.props.liveGameController.getDatabaseVal("c", (players) => players && res(Object.keys(players)))) : [];
                        }
                    }],
                    run: function (target) {
                        let stateNode = getStateNode();
                        stateNode.props.liveGameController.getDatabaseVal("c", (players) => {
                            let player;
                            if (players && (player = Object.entries(players).find((x) => x[0].toLowerCase() == target.toLowerCase()))) {
                                const cr = player[1].cr;
                 
