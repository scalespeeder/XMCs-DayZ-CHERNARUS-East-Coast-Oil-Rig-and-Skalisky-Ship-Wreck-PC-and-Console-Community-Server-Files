DayZ Chernarus East Coast Big Oil Rig & Skalisky Ship Wreck  By XMC , For Console and PC xml json Mod Instructions & Terms Of Use

These files spawn a large oil rig, with loot, in the sea 1km North East Of Solnichniy on the East Coast Of Chernarus.

AND a ship wreck between Skalisky Island & the main land.

Limited Testing on PC Chernaus Local Server DAYZ Exp Version 1.26 Aug 2024.

BIG THANKS TO: XMC 

His Orginal Github, with the Oil Rig Spawning South of Chernogorsk: https://github.com/XMC-Cross/XMCs-Oil-Rig

Many Thanks To Inclement Dab for his amazing DayZ Editor that makes this all possible: https://steamcommunity.com/sharedfiles/filedetails/?id=2250764298

TERMS OF USE
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS
OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Using these modded xml / json files and instructions could break the functioning of your DAYZ server, requiring a reinstall that would wipe
all player progress.

Using these modded files neccessitates increased regular restarts to prevent server crashing.

It is suggested you thoroughly test your server after applying these files to ensure proper
functioning of your server.

I always recomend you validate your files at: https://www.xmlvalidation.com/ and https://jsonformatter.curiousconcept.com/

The DayZ Editor Mod .dze files are included for those who are familiar with the mod & how to create custom objects: xmc-oil-rig-and-wreck-alt.dze

Instructions:

Click the "Code" button and "Download Zip" on the Github Repository and extract the files on your local PC for access.

Ensure your DayZ Server has activated the cfggameplay.json. For console users on Nitrado Servers, go to "General Settings" on your server and tick "Enable cfggameplay.json".

On PC Servers add the following line to your serverDZ.cfg:

enableCfgGameplayFile = 1;

(On some PC servers, including Nitrado, the serverDZ.cfg is "hidden", so you need to enable "expert mode" in settings,
then go to "expert settings", which is the serverDZ.cfg. Stop the server before making changes this way.)

Upload "xmc-oil-rig-and-wreck-objects-alt.json" from the extracted files to inside the "custom" folder of the mission directory on your server. This file places the structures on your map.
(If you haven't got a "custom" folder, create one.)

Open the cfggameplay.json file in the correct mission file for your server and look for the "objectSpawnersArr" line.

This file tells your server to access your custom file.

Edit it to look like this if you just want the oil rig: 

	"objectSpawnersArr": ["custom/xmc-oil-rig-and-wreck-objects-alt.json"],
	
If you already are calling custom jsons to spawn items, seperate the files like this:

	"objectSpawnersArr": ["custom/xmc-oil-rig-and-wreck-objects-alt.json","custom/differentfile.json"],
	
Save your changes & upload if you need to.

Next we need to add the new loot references to mapgroupproto.xml, near the top below </defaults> :

<group name="StaticObj_Wreck_Mi8" lootmax="5">
				<usage name="Military" />
				<container name="lootShelves">
					<category name="tools" />
					<category name="containers" />
					<category name="food" />
					<tag name="shelves" />
					<point pos="-6.850625 -1.421773 -0.344947" range="0.1" height="0.2" /> 
					<point pos="-5.945957 -1.428432 -0.428892" range="0.1" height="0.2" /> 
					<point pos="-4.351717 -1.458216 -0.654538" range="0.1" height="0.2" /> 
					<point pos="-3.668689 -1.460896 -0.707812" range="0.1" height="0.2" /> 
					<point pos="-2.788545 -1.477059 -0.737154" range="0.1" height="0.2" /> 
					<point pos="-2.747982 -1.500877 -2.690142" range="0.1" height="0.2" /> 
				</container>
				<container name="lootFloor">
					<category name="tools" />
					<category name="clothes" />
					<category name="containers" />
					<tag name="floor" />
					<point pos="-7.730903 -1.702977 -1.841105" range="0.7" height="1" /> 
					<point pos="-7.601032 -1.755581 -0.854871" range="0.7" height="1" /> 
					<point pos="-6.134241 -1.736838 -1.913590" range="1" height="2" /> 
					<point pos="-5.533698 -1.801026 -1.201971" range="1.5" height="2" /> 
					<point pos="-5.086518 -1.746938 -1.986828" range="1" height="2" /> 
					<point pos="-4.126190 -1.694655 -2.120756" range="1.5" height="2" /> 
					<point pos="-3.625636 -1.771201 -1.275335" range="2" height="2" /> 
				</container>
				<container name="lootWeapons" lootmax="2">
					<category name="weapons" />
					<point pos="-5.230893 -1.447002 -0.552535" range="0.1" height="0.2" /> 
					<point pos="-6.382368 -1.783770 -1.002696" range="0.7" height="1" /> 
					<point pos="-6.858212 -1.741839 -1.450104" range="1" height="1" />
					<point pos="-2.930845 -1.680517 -2.063365" range="2" height="2" />
					<point pos="-4.609527 -1.812918 -1.295148" range="1.5" height="2" /> 
					<point pos="-3.567614 -1.522260 -2.499196" range="0.1" height="0.2" /> 
				</container>
			</group>
  		<group name="StaticObj_ammoboxes_single" lootmax="2">
  			<usage name="Military" />
  			<container name="lootWeapons" lootmax="2">
  						<category name="weapons" />
  						<point pos="0.012415 -0.107530 -0.091038" range="0.4" height="0.5" /> 
  						<point pos="-0.254196 -0.107530 0.627266" range="0.1" height="0.2" /> 
  						<point pos="-0.020935 -0.107530 -0.730989" range="0.1" height="0.2" /> 
  			</container>
  		</group>
  		<group name="StaticObj_ammoboxes_stacked" lootmax="1">
  			<usage name="Military" />
  			<container name="lootWeapons" lootmax="1">
  						<category name="weapons" />
  						<point pos="-0.034654 0.776729 -0.013322" range="1" height="1" /> 
  			</container>
  		</group>
  		<group name="StaticObj_Wreck_Ship_Big_FrontA" lootmax="6">
  				<usage name="Industrial" />
  				<usage name="Coast" />
  				<container name="lootFloor1" lootmax="4">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-6.419189 -17.062881 -2.890381" range="1.199951" height="2.000000" />
  						<point pos="-6.983640 -10.462875 -12.019044" range="1.199951" height="2.000000" />
  						<point pos="-3.400878 -10.462875 -15.116943" range="1.199951" height="2.000000" />
  						<point pos="-8.412109 -10.462875 -7.199221" range="1.199951" height="2.000000" />
  						<point pos="-3.506102 -10.462875 -10.031738" range="1.199951" height="2.000000" />
  						<point pos="1.779053 -10.462875 -7.411622" range="1.199951" height="2.000000" />
  						<point pos="-5.447021 -10.462875 -17.988037" range="1.199951" height="2.000000" />
  						<point pos="0.181642 -10.462875 -12.100099" range="1.199951" height="2.000000" />
  						<point pos="-9.760255 -8.969162 -2.999267" range="1.199951" height="2.000000" />
  						<point pos="-10.488282 -8.969162 2.778072" range="1.199951" height="2.000000" />
  						<point pos="3.168945 -8.958107 -2.925781" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootFloor2" lootmax="4">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="3.550048 -5.662880 -6.760253" range="1.199951" height="2.000000" />
  						<point pos="-11.638917 -5.671654 3.239256" range="1.199951" height="2.000000" />
  						<point pos="-9.571289 -5.671654 0.082517" range="1.199951" height="2.000000" />
  						<point pos="5.281738 -5.671654 2.933348" range="1.199951" height="2.000000" />
  						<point pos="-9.547118 -5.662872 -9.172853" range="1.199951" height="2.000000" />
  						<point pos="-7.164063 -5.662872 -5.924560" range="0.505615" height="1.264038" />
  						<point pos="-9.547116 -5.662872 -13.672119" range="1.199951" height="2.000000" />
  						<point pos="3.280759 -5.662880 -11.974854" range="1.199951" height="2.000000" />
  						<point pos="2.837889 -5.662880 -16.870117" range="1.028125" height="2.000000" />
  						<point pos="-10.924077 -3.033089 -14.588133" range="1.199951" height="2.000000" />
  						<point pos="3.642578 -3.270432 -4.772461" range="1.199951" height="2.000000" />
  						<point pos="2.108885 -3.139740 -10.196777" range="1.199951" height="2.000000" />
  						<point pos="-10.151124 -3.274918 -4.584472" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootFloor3" lootmax="4">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="2.860595 -2.197670 -25.912596" range="0.100000" height="0.250000" />
  						<point pos="-7.767576 -2.128906 -30.850100" range="0.100000" height="0.250000" />
  						<point pos="-9.227296 -2.249985 -25.915039" range="0.134375" height="0.335938" />
  						<point pos="-7.541012 -2.120819 -31.338619" range="0.134375" height="0.335938" />
  						<point pos="-9.391602 -2.251266 -25.410400" range="0.134375" height="0.335938" />
  						<point pos="1.213135 -2.082458 -31.385500" range="0.134375" height="0.335938" />
  						<point pos="1.397701 -2.080994 -30.874758" range="0.134375" height="0.335938" />
  						<point pos="3.066163 -2.196503 -25.446043" range="0.134375" height="0.335938" />
  						<point pos="-3.123783 -2.910545 -20.494629" range="0.932129" height="1.999996" />
  						<point pos="2.579099 -2.946297 -18.223633" range="1.199951" height="2.000000" />
  						<point pos="1.364994 -2.794647 -24.196043" range="1.199951" height="2.000000" />
  						<point pos="1.626954 -2.717445 -27.794680" range="1.199951" height="2.000000" />
  						<point pos="-0.282470 -2.603836 -32.698238" range="1.199951" height="2.000000" />
  						<point pos="-5.425293 -2.606750 -32.570072" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootfirearms" lootmax="3">
  						<category name="weapons" />
  						<category name="explosives" />
  						<point pos="4.378663 -8.948456 3.482177" range="1.199951" height="2.000000" />
  						<point pos="-1.204590 -10.462875 -18.098875" range="1.199951" height="2.000000" />
  						<point pos="-3.120360 -5.662872 -22.259035" range="1.199951" height="2.000008" />
  						<point pos="1.226563 -17.055489 3.325195" range="1.199951" height="2.000000" />
  						<point pos="-3.029541 -17.075409 0.304444" range="1.199951" height="2.000000" />
  						<point pos="5.093259 -3.046303 -14.039063" range="1.199951" height="2.000000" />
  						<point pos="-7.846675 -2.714684 -27.914309" range="1.199951" height="2.000000" />
  						<point pos="-8.402833 -2.961372 -17.615234" range="1.199951" height="2.000000" />
  						<point pos="0.607422 -3.242210 -5.954834" range="0.869873" height="2.000000" />
  						<point pos="-8.636228 -3.177734 -8.625491" range="1.199951" height="2.000000" />
  						<point pos="3.658447 -5.671654 0.041992" range="1.199951" height="2.000000" />
  						<point pos="-1.936279 -5.662872 -5.897949" range="0.479004" height="1.197510" />
  						<point pos="-6.910886 -5.662880 -24.297363" range="1.199951" height="2.000000" />
  						<point pos="0.120115 -5.662872 -24.338379" range="1.199951" height="2.000000" />
  						<point pos="-7.422365 -17.062881 2.751952" range="1.199951" height="2.000000" />
  				</container>
  		</group>
  		<group name="StaticObj_Wreck_Ship_Big_FrontB" lootmax="6">
  				<usage name="Industrial" />
  				<usage name="Coast" />
  				<container name="lootFloor1" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-3.871092 -15.554062 -2.926759" range="1.199951" height="1.875999" />
  						<point pos="-7.565917 -15.554062 -3.071045" range="1.199951" height="1.807358" />
  						<point pos="-7.961425 -15.554062 0.554199" range="1.199951" height="1.812126" />
  						<point pos="-5.352295 -15.554062 -0.557618" range="1.199951" height="1.862556" />
  						<point pos="-2.624756 -15.554062 0.393310" range="1.199951" height="1.922905" />
  						<point pos="-4.832035 -15.550316 14.462400" range="1.199951" height="1.908638" />
  				</container>
  				<container name="lootFloor2" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-9.916749 -7.468216 13.619381" range="0.959375" height="1.857941" />
  						<point pos="-9.938965 -7.464897 2.408446" range="0.959375" height="1.800568" />
  						<point pos="6.938963 -7.464897 -11.223877" range="1.199951" height="2.020721" />
  						<point pos="3.996337 -7.464897 -7.190917" range="1.199951" height="2.011353" />
  						<point pos="-5.445311 -7.464897 -7.485597" range="1.199951" height="1.858780" />
  						<point pos="-8.495608 -7.464897 -12.972168" range="1.199951" height="1.775391" />
  						<point pos="-8.613279 -7.464897 -7.750001" range="1.199951" height="1.791718" />
  				</container>
  				<container name="lootFloor3" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="8.503417 -4.167389 14.244140" range="1.064209" height="2.045570" />
  						<point pos="8.506104 -4.167389 7.217772" range="1.066162" height="2.040527" />
  						<point pos="-10.238037 -4.167358 2.270994" range="1.094238" height="1.793739" />
  						<point pos="-10.260499 -4.193161 12.938962" range="1.117676" height="1.960632" />
  						<point pos="-10.268798 -4.167358 5.481201" range="1.124756" height="1.804649" />
  						<point pos="-10.277099 -4.167358 9.163330" range="1.133545" height="1.817696" />
  						<point pos="8.577393 -4.167389 10.566650" range="1.137939" height="2.043236" />
  						<point pos="-7.198977 -4.167374 -13.485108" range="1.145996" height="1.800644" />
  						<point pos="8.613524 -4.167389 1.034178" range="1.174072" height="2.036530" />
  						<point pos="5.524169 -4.167389 -13.681396" range="1.179688" height="2.013077" />
  				</container>
  				<container name="lootFloor4" lootmax="1">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-6.745117 -1.146820 -6.634278" range="0.707273" height="1.620110" />
  						<point pos="9.108153 -1.146820 -6.806886" range="0.787500" height="1.968750" />
  						<point pos="5.041993 -1.146820 -3.192139" range="0.821875" height="1.998650" />
  						<point pos="9.000244 -1.146820 -3.247072" range="0.890625" height="2.031113" />
  						<point pos="8.575927 -1.146820 -5.078125" range="0.984440" height="2.028023" />
  				</container>
  				<container name="lootfirearms" lootmax="3">
  						<category name="explosives" />
  						<category name="weapons" />
  						<point pos="-7.870358 -15.554062 14.052245" range="1.199951" height="1.862556" />
  						<point pos="-6.483398 -7.464897 -3.036133" range="1.199951" height="1.853096" />
  						<point pos="-2.397949 -1.146820 -3.645996" range="1.199951" height="1.916344" />
  						<point pos="-2.060547 -1.146820 -6.357422" range="1.199951" height="1.913635" />
  						<point pos="-9.622558 -4.167351 -13.529054" range="1.199951" height="1.749832" />
  						<point pos="7.918213 -4.167389 -9.878419" range="1.199951" height="2.025803" />
  						<point pos="1.011230 -1.146820 -4.791992" range="1.199951" height="1.983330" />
  						<point pos="-5.969973 -15.554062 11.485106" range="1.199951" height="1.892960" />
  						<point pos="-10.208496 -1.146820 -3.540042" range="1.199951" height="1.753876" />
  						<point pos="-7.328366 -4.167374 -10.221926" range="1.199951" height="1.809685" />
  						<point pos="6.195312 -7.464890 -3.034180" range="1.199951" height="2.023506" />
  						<point pos="1.020019 -15.554062 8.783936" range="1.199951" height="1.583023" />
  						<point pos="8.479738 -7.464897 15.260987" range="1.076542" height="2.000000" />
  				</container>
  		</group>
  		<group name="StaticObj_Wreck_Ship_Big_BackA" lootmax="6">
  				<usage name="Industrial" />
  				<usage name="Coast" />
  				<container name="lootFloor1" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-1.311035 -17.003929 -1.717529" range="1.199951" height="2.000023" />
  						<point pos="-6.891846 -17.003929 -1.521974" range="1.199951" height="2.000023" />
  						<point pos="-4.176759 -17.003929 -3.900880" range="1.199951" height="2.000023" />
  						<point pos="-1.294191 -17.003929 -10.496095" range="1.199951" height="2.000023" />
  						<point pos="-7.496825 -17.003929 -12.462158" range="1.199951" height="2.000023" />
  				</container>
  				<container name="lootFloor2" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-5.612305 -8.910210 0.563720" range="1.199951" height="2.000008" />
  						<point pos="-2.671631 -8.910217 -17.678955" range="0.340625" height="0.851563" />
  						<point pos="-8.769529 -8.910210 -4.629397" range="0.959375" height="2.000008" />
  						<point pos="-2.705323 -8.910210 -14.357667" range="1.062500" height="2.000008" />
  						<point pos="1.808349 -8.910210 -14.361816" range="1.062500" height="2.000008" />
  						<point pos="9.562255 -8.910210 -5.815673" range="1.131250" height="2.000008" />
  				</container>
  				<container name="lootFloor3" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="9.590332 -5.612701 -2.988526" range="0.991455" height="2.000000" />
  						<point pos="-9.107422 -5.612701 -6.806885" range="0.787500" height="1.968750" />
  						<point pos="-9.031251 -5.612701 1.214111" range="1.028125" height="2.000000" />
  						<point pos="9.753417 -5.612701 -14.306396" range="1.134521" height="2.000000" />
  						<point pos="9.799560 -5.612701 -7.915528" range="1.199951" height="2.000000" />
  						<point pos="-9.214358 -5.612701 -12.270264" range="1.199951" height="2.000000" />
  						<point pos="-9.230713 -5.612701 -4.340820" range="1.199951" height="2.000000" />
  						<point pos="9.795410 -5.612701 1.856199" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootfirearms" lootmax="3">
  						<category name="explosives" />
  						<category name="weapons" />
  						<point pos="-2.041016 -17.003929 -6.854737" range="1.199951" height="2.000023" />
  						<point pos="-7.072265 -17.003929 -8.246338" range="1.199951" height="2.000023" />
  						<point pos="-5.496581 -2.596138 -15.438477" range="1.199951" height="2.000008" />
  						<point pos="0.458985 -2.596138 -16.962891" range="1.199951" height="2.000008" />
  						<point pos="6.937987 -2.596138 -16.020508" range="1.199951" height="2.000008" />
  						<point pos="-3.401855 -5.612701 1.038330" range="1.199951" height="2.000000" />
  						<point pos="2.824463 -5.612701 0.812988" range="1.199951" height="2.000000" />
  						<point pos="-6.273195 -8.911217 -17.441404" range="0.821875" height="2.000000" />
  				</container>
  		</group>
  		<group name="StaticObj_Wreck_Ship_Big_BackB" lootmax="6">
  				<usage name="Industrial" />
  				<usage name="Coast" />
  				<container name="lootFloor1" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-4.670908 -7.888664 26.930416" range="1.199951" height="2.000000" />
  						<point pos="1.020757 -7.888657 20.576660" range="1.199951" height="2.000000" />
  						<point pos="-6.341553 -7.888657 15.273925" range="1.199951" height="2.000000" />
  						<point pos="4.479253 -7.888664 26.186523" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootFloor2" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="6.305418 -4.088692 27.368408" range="1.199951" height="2.000000" />
  						<point pos="-8.123780 -4.088669 13.812499" range="1.199951" height="2.000000" />
  						<point pos="-6.876952 -4.088661 19.833986" range="1.199951" height="2.000000" />
  						<point pos="2.284424 -4.088654 13.596435" range="1.199951" height="2.000000" />
  						<point pos="7.741943 -4.088669 15.014649" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootFloor3" lootmax="4">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<tag name="shelves" />
  						<point pos="-5.288336 -1.387939 28.207520" range="0.546875" height="1.367188" />
  						<point pos="-0.081791 -1.387939 28.079592" range="0.650000" height="1.625000" />
  						<point pos="2.351326 -1.387939 28.066404" range="0.684375" height="1.710938" />
  						<point pos="-2.953362 -1.387939 28.055174" range="0.716064" height="1.790160" />
  						<point pos="9.094975 -1.387939 16.827879" range="0.959375" height="2.000000" />
  						<point pos="8.014406 -1.387939 23.336426" range="1.199951" height="2.000000" />
  						<point pos="-7.339844 -1.387939 25.094725" range="1.199951" height="2.000000" />
  						<point pos="-7.368405 -1.387939 21.431643" range="1.199951" height="2.000000" />
  						<point pos="-7.030031 -1.387939 17.625488" range="1.199951" height="2.000000" />
  						<point pos="7.829099 -1.387939 26.640383" range="1.199951" height="2.000000" />
  						<point pos="6.193851 -1.387939 18.488279" range="1.199951" height="2.000000" />
  						<point pos="8.316410 -0.799210 18.575926" range="0.100000" height="0.250000" />
  						<point pos="-8.709226 -0.792671 18.036379" range="0.134375" height="0.335938" />
  						<point pos="-0.145512 1.107010 12.318849" range="0.937055" height="2.000000" />
  				</container>
  				<container name="lootfirearms" lootmax="2">
  						<category name="explosives" />
  						<category name="weapons" />
  						<point pos="5.640379 -7.888657 17.344482" range="1.199951" height="2.000000" />
  						<point pos="-8.754393 -0.798393 18.545168" range="0.134375" height="0.335938" />
  						<point pos="4.331551 -1.387939 28.181149" range="0.546875" height="1.367188" />
  						<point pos="-6.713624 -4.088661 26.956787" range="1.199951" height="2.000000" />
  				</container>
  		</group>
  		<group name="StaticObj_Wreck_Ship_Big_Castle" lootmax="25">
  				<usage name="Industrial" />
  				<usage name="Coast" />
  				<container name="lootFloor1" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<point pos="-3.113038 -16.946526 2.968260" range="1.199951" height="2.000343" />
  						<point pos="3.030518 -16.946526 3.119628" range="1.199951" height="2.000343" />
  						<point pos="-1.461914 -14.254990 -0.258301" range="1.199951" height="2.000000" />
  						<point pos="-3.541015 -14.254990 -3.188477" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootFloor2" lootmax="5">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<point pos="-0.229492 -11.545486 -2.848633" range="1.199951" height="2.000000" />
  						<point pos="-3.829101 -11.545486 -2.819092" range="1.199951" height="2.000000" />
  						<point pos="-7.532472 -11.545486 -2.286865" range="1.199951" height="2.000000" />
  						<point pos="7.163086 -11.545486 13.320312" range="1.199951" height="2.000015" />
  						<point pos="6.944580 -11.545486 5.753660" range="1.199951" height="2.000015" />
  						<point pos="-6.811279 -11.545486 -6.317383" range="1.199951" height="2.000000" />
  						<point pos="5.055665 -11.545486 -6.264648" range="1.199951" height="2.000008" />
  						<point pos="-7.715328 -11.545486 14.718505" range="1.115234" height="2.000000" />
  						<point pos="-7.738038 -11.545486 10.862791" range="1.137939" height="2.000000" />
  						<point pos="4.048583 -11.545486 -2.850097" range="1.151367" height="2.000000" />
  						<point pos="-6.194337 -11.545486 6.358641" range="1.094238" height="2.000000" />
  						<point pos="-5.771727 -11.545486 11.412842" range="0.671143" height="1.677858" />
  						<point pos="-5.800540 -11.545486 14.311766" range="0.699463" height="1.748657" />
  						<point pos="-9.809329 -11.545479 14.487790" range="0.809570" height="2.000008" />
  						<point pos="9.914554 -11.545486 12.905761" range="0.821875" height="2.000015" />
  						<point pos="-9.867434 -11.545486 5.994139" range="0.867676" height="2.000015" />
  						<point pos="9.885742 -11.545486 3.026122" range="0.885742" height="2.000015" />
  						<point pos="8.010986 -11.545486 -2.520996" range="0.901367" height="1.997169" />
  						<point pos="3.174809 -11.545486 19.069578" range="0.996094" height="1.999847" />
  						<point pos="-7.343506 -11.545486 18.895750" range="1.185303" height="2.000015" />
  						<point pos="-7.676270 -11.545486 2.200927" range="1.199951" height="2.000000" />
  				</container>
  				<container name="lootFloor3" lootmax="2">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<point pos="-9.657959 -8.846199 0.290283" range="1.152588" height="2.000008" />
  						<point pos="9.722417 -8.846199 14.657957" range="1.028125" height="1.902893" />
  						<point pos="9.679443 -8.846199 16.924801" range="1.062500" height="1.966789" />
  						<point pos="-9.487304 -8.846199 16.964355" range="0.909378" height="2.000008" />
  						<point pos="-3.586914 -8.846199 -2.727295" range="0.986816" height="2.000008" />
  						<point pos="9.808106 -8.846199 2.570312" range="0.988770" height="2.000008" />
  						<point pos="9.202638 -8.846199 7.356934" range="0.702082" height="1.755205" />
  						<point pos="-2.588379 -8.846199 2.118896" range="1.199951" height="2.000008" />
  						<point pos="2.500976 -8.846199 1.609130" range="1.199951" height="2.000008" />
  						<point pos="5.703856 -8.846199 -2.347656" range="1.195557" height="2.000008" />
  						<point pos="-9.367188 -8.846199 3.233644" range="1.199951" height="2.000008" />
  						<point pos="-1.165283 -8.846199 -2.626709" range="1.199951" height="2.000008" />
  						<point pos="-5.991456 -8.846199 18.779539" range="1.199951" height="2.000008" />
  						<point pos="6.071536 -8.846199 18.879883" range="1.199951" height="2.000008" />
  						<point pos="-9.530272 -8.846199 14.855711" range="1.199951" height="2.000008" />
  						<point pos="9.501221 -8.846199 0.260254" range="1.199951" height="2.000008" />
  						<point pos="3.433351 -8.846199 4.615966" range="1.199951" height="2.000008" />
  						<point pos="-3.488769 -8.846199 4.794921" range="1.199951" height="1.709892" />
  						<point pos="-7.747803 -7.863258 18.816162" range="0.203125" height="0.507813" />
  						<point pos="-7.743895 -7.863258 13.188231" range="0.203125" height="0.507813" />
  						<point pos="7.769779 -7.863266 12.589844" range="0.203125" height="0.507813" />
  						<point pos="7.739991 -7.863266 18.218994" range="0.203125" height="0.507813" />
  						<point pos="9.790774 -6.214699 16.876951" range="1.096875" height="2.631523" />
  						<point pos="-3.563233 -6.145805 1.072508" range="1.199951" height="1.516701" />
  						<point pos="2.759278 -6.145805 1.055175" range="1.199951" height="2.000008" />
  						<point pos="9.486084 -6.145805 3.893065" range="1.199951" height="2.000015" />
  						<point pos="7.551514 -6.145805 5.782958" range="1.199951" height="2.000015" />
  						<point pos="9.397218 -6.145805 1.127440" range="1.199951" height="2.000015" />
  						<point pos="7.427978 -6.145805 -1.892823" range="1.199951" height="2.000008" />
  						<point pos="-1.783447 -6.145805 -1.558594" range="1.199951" height="2.000008" />
  						<point pos="0.985840 -6.145805 -2.501221" range="1.199951" height="2.000008" />
  						<point pos="-8.404299 -6.145805 5.824703" range="1.199951" height="2.000015" />
  						<point pos="3.587893 -6.145805 12.878173" range="1.199951" height="2.000008" />
  						<point pos="-3.371095 -6.145805 12.861815" range="1.199951" height="2.000008" />
  						<point pos="9.745367 -5.753654 14.217037" range="1.199951" height="2.193985" />
  						<point pos="-9.861814 -5.753647 14.197510" range="1.199951" height="2.197990" />
  						<point pos="-9.762943 -5.753647 17.273436" range="1.199951" height="2.200157" />
  				</container>
  				<container name="lootFloor4" lootmax="3">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<tag name="floor" />
  						<point pos="6.671875 -3.446808 -1.537110" range="1.185059" height="2.000015" />
  						<point pos="1.327392 -3.446800 -2.420410" range="1.199951" height="2.000008" />
  						<point pos="-1.576904 -3.446800 -2.104492" range="1.199951" height="2.000008" />
  						<point pos="-7.189697 -3.446800 5.868161" range="1.199951" height="2.000008" />
  						<point pos="6.981446 -3.446800 5.491210" range="1.199951" height="2.000008" />
  						<point pos="0.002441 -0.753403 -2.931152" range="1.176270" height="2.000000" />
  						<point pos="-4.850342 -0.752792 1.496338" range="1.199951" height="1.996948" />
  						<point pos="6.691651 -0.752769 1.914794" range="1.199951" height="1.996803" />
  				</container>
  				<container name="lootshelves1" lootmax="4">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<category name="food" />
  						<category name="books" />
  						<tag name="shelves" />
  						<point pos="-2.575195 -2.340828 -3.474853" range="0.100000" height="0.250000" />
  						<point pos="0.304931 -2.112373 -3.423340" range="0.100000" height="0.250000" />
  						<point pos="-0.296631 -2.124092 -3.399658" range="0.100000" height="0.250000" />
  						<point pos="4.712402 -2.325745 -3.194092" range="0.134375" height="0.335938" />
  						<point pos="5.734863 -2.342789 -2.998780" range="0.134375" height="0.335938" />
  						<point pos="7.764403 -13.396255 -3.340088" range="0.134375" height="0.264999" />
  						<point pos="-4.462891 -2.412804 -2.990724" range="0.134375" height="0.335938" />
  						<point pos="3.175781 -2.363510 -3.294677" range="0.134375" height="0.335938" />
  						<point pos="4.048584 -2.357674 -3.189942" range="0.134375" height="0.335938" />
  				</container>
  				<container name="lootshelves2" lootmax="10">
  						<category name="tools" />
  						<category name="containers" />
  						<category name="clothes" />
  						<category name="food" />
  						<category name="books" />
  						<tag name="shelves" />
  						<point pos="7.313476 -12.659645 -0.100098" range="0.151367" height="0.164352" />
  						<point pos="7.748290 -13.855202 3.720214" range="0.237500" height="0.593750" />
  						<point pos="-8.710694 -13.021004 10.451413" range="0.271875" height="0.679688" />
  						<point pos="8.809082 -13.810997 1.255615" range="0.306250" height="0.533005" />
  						<point pos="8.959718 -13.810997 4.935058" range="0.306250" height="0.533066" />
  						<point pos="-8.962891 -13.020676 8.585445" range="0.306250" height="0.765625" />
  						<point pos="8.910645 -13.020340 17.207518" range="0.306250" height="0.765625" />
  						<point pos="8.003905 -13.021248 -2.248779" range="0.340625" height="0.834351" />
  						<point pos="8.328368 -13.021095 1.201660" range="0.340625" height="0.834198" />
  						<point pos="8.058106 -13.021278 -0.458497" range="0.340625" height="0.851563" />
  						<point pos="-8.173342 -13.021286 20.403807" range="0.340625" height="0.851563" />
  						<point pos="-9.058840 -13.810997 17.214109" range="0.340625" height="0.533066" />
  						<point pos="-8.477044 -13.021156 17.196779" range="0.340625" height="0.851563" />
  						<point pos="-9.594240 -13.810997 8.533690" range="0.340625" height="0.533607" />
  						<point pos="9.580077 -13.019890 7.010254" range="0.340625" height="0.851563" />
  						<point pos="8.629150 -13.810997 7.007324" range="0.340625" height="0.532486" />
  						<point pos="-8.777833 -13.810997 10.523191" range="0.340625" height="0.532600" />
  						<point pos="-8.799561 -13.021225 1.283202" range="0.340625" height="0.851563" />
  						<point pos="-8.437499 -13.021194 15.527830" range="0.443750" height="0.834328" />
  						<point pos="8.272708 -13.810997 17.280272" range="0.375000" height="0.532410" />
  						<point pos="9.009766 -13.810997 2.471191" range="0.375000" height="0.532364" />
  						<point pos="8.283446 -13.021271 4.889405" range="0.375000" height="0.834366" />
  						<point pos="-8.599121 -13.810997 8.508545" range="0.375000" height="0.532402" />
  						<point pos="9.157470 -13.810997 -0.427003" range="0.375000" height="0.533569" />
  						<point pos="-9.296388 -13.810997 18.546631" range="0.375000" height="0.533493" />
  						<point pos="-9.669926 -13.810997 10.531491" range="0.375000" height="0.533676" />
  						<point pos="-8.241457 -13.021301 18.537594" range="0.375000" height="0.937500" />
  						<point pos="-9.172115 -13.810997 20.435791" range="0.375000" height="0.533432" />
  						<point pos="9.161864 -13.810997 -2.212159" range="0.375000" height="0.533669" />
  						<point pos="-9.202641 -13.810997 15.970212" range="0.409375" height="0.533386" />
  						<point pos="-8.686522 -13.810997 1.278563" range="0.340625" height="0.532158" />
  						<point pos="7.800780 -14.151253 -3.369386" range="0.100000" height="0.250000" />
  						<point pos="7.299072 -14.210243 -0.141847" range="0.155762" height="0.389405" />
  				</container>
  				<container name="lootweapons" lootmax="8">
  						<category name="weapons" />
  						<category name="explosives" />
  						<point pos="7.395996 -14.210243 17.488770" range="0.156738" height="0.391845" />
  						<point pos="8.127929 -13.021286 17.170654" range="0.271875" height="0.679688" />
  						<point pos="9.339598 -13.810997 17.274660" range="0.375000" height="0.533699" />
  						<point pos="10.142577 -8.846199 9.094237" range="0.663330" height="1.658325" />
  						<point pos="-9.948973 -8.846199 9.185547" range="0.756348" height="1.890870" />
  						<point pos="9.770021 -11.545486 19.123777" range="0.769531" height="1.923828" />
  						<point pos="9.807372 -11.545486 7.082032" range="0.806885" height="2.000015" />
  						<point pos="-9.922851 -11.545479 11.372313" range="0.821875" height="2.000008" />
  						<point pos="8.431152 -8.846199 3.786376" range="0.849007" height="2.000008" />
  						<point pos="10.045654 -3.446800 3.267090" range="0.856250" height="2.000008" />
  						<point pos="9.917237 -8.846199 5.934570" range="0.890137" height="2.000008" />
  						<point pos="3.559570 -8.846199 -2.686035" range="0.959473" height="2.000008" />
  						<point pos="-0.119386 -8.846199 19.149170" range="0.997314" height="2.000008" />
  						<point pos="-0.878903 -11.545486 19.077148" range="1.003418" height="1.998283" />
  						<point pos="3.921390 -6.145805 16.830324" range="1.028125" height="2.000008" />
  						<point pos="-4.178952 -3.446800 7.607911" range="1.131250" height="2.000008" />
  						<point pos="-9.639163 -6.145805 3.654293" range="1.131250" height="2.000015" />
  						<point pos="6.574951 -0.753387 -2.518800" range="1.133301" height="1.999924" />
  						<point pos="4.863037 -6.145805 -2.414063" range="1.137207" height="2.000008" />
  						<point pos="-5.715821 -8.846199 -1.993164" range="1.184082" height="2.000008" />
  						<point pos="-6.643311 -0.753387 -2.446045" range="1.196045" height="1.999924" />
  						<point pos="-4.661377 -6.145805 -1.842042" range="1.199951" height="2.000008" />
  						<point pos="-9.366700 -6.145805 -1.220948" range="1.199951" height="2.000008" />
  						<point pos="6.881595 -11.545486 9.634521" range="1.199951" height="2.000015" />
  						<point pos="4.412598 -3.446800 7.078124" range="1.199951" height="2.000008" />
  						<point pos="-9.426761 -8.846199 6.836421" range="1.199951" height="2.000008" />
  						<point pos="-8.343507 -8.846199 -1.730469" range="1.199951" height="2.000008" />
  						<point pos="-2.709473 -11.545486 -6.245606" range="1.199951" height="2.000008" />
  						<point pos="-0.119629 -16.946526 3.138427" range="1.199951" height="2.000343" />
  						<point pos="-9.508545 -3.446808 2.734617" range="1.199951" height="2.000015" />
  						<point pos="8.260986 -8.846199 -1.812501" range="1.199951" height="2.000008" />
  						<point pos="-7.561036 -6.145805 0.970702" range="1.199951" height="2.000000" />
  						<point pos="-0.079839 -6.145805 15.217529" range="1.199951" height="2.000000" />
  						<point pos="7.847900 -11.545486 2.033935" range="1.058349" height="2.000000" />
  						<point pos="8.375736 -11.545486 18.229002" range="0.456299" height="1.140747" />
  						<point pos="-3.165771 -16.946526 6.819825" range="1.038574" height="1.508690" />
  						<point pos="7.575199 -11.545486 19.307861" range="0.774170" height="1.935425" />
  						<point pos="9.220947 -13.020958 2.503172" range="0.443402" height="1.046387" />
  						<point pos="2.941162 -16.946526 6.952148" range="0.906250" height="1.600876" />
  						<point pos="-3.865231 -6.145805 16.585203" range="1.199951" height="2.000008" />
  						<point pos="1.294434 -8.846199 -2.249512" range="1.199951" height="2.000008" />
  				</container>
  		</group>
	
Next we add loot to the structures by adding the following code snippet to the top of your mapgrouppos.xml file, after <map> 

	<!--east coast oil rig loot-->
	<group name="StaticObj_Cemetery_SmallCross" pos="24000.000000 25.912701 0.021014" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Wreck_Ship_Big_FrontA" pos="13054.178711 11.284058 3445.106201" rpy="0.000000 0.999988 -55.050049" a="145.05"/>
	<group name="StaticObj_Wreck_Ship_Big_FrontB" pos="13044.674805 9.781555 3427.479492" rpy="0.000000 0.000000 -55.050045" a="145.05"/>
	<group name="StaticObj_Wreck_Ship_Big_BackA" pos="13013.000000 11.227800 3399.989990" rpy="0.000000 0.000000 -36.858398" a="126.858"/>
	<group name="StaticObj_Wreck_Ship_Big_BackB" pos="12996.874023 9.717102 3388.693359" rpy="0.000000 0.000000 -36.858379" a="126.858"/>
	<group name="StaticObj_Wreck_Ship_Big_Castle" pos="13006.155273 19.898897 3395.365479" rpy="0.000000 0.000000 -36.858337" a="126.858"/>
	<group name="Land_Tisy_RadarPlatform_Top" pos="14522.797852 0.904145 7300.208496" rpy="0.000000 0.000000 144.999969" a="-55"/>
	<group name="Land_Construction_Crane" pos="14592.304688 49.884308 7259.055664" rpy="0.000000 0.000000 -37.454380" a="127.454"/>
	<group name="Land_Castle_Stairs" pos="14515.212891 1.227014 7321.838379" rpy="0.000000 0.000000 143.902222" a="-53.9022"/>
	<group name="Land_Pier_Crane_A" pos="14524.392578 13.552427 7309.498047" rpy="0.000000 0.000000 -126.044060" a="-143.956"/>
	<group name="Land_Pier_Crane_B" pos="14530.002930 26.670158 7311.048828" rpy="0.000000 0.000000 -25.045582" a="115.046"/>
	<group name="Land_Container_1Mo" pos="14514.666016 9.397530 7297.879395" rpy="0.000000 0.000000 4.107001" a="85.893"/>
	<group name="Land_Container_1Mo" pos="14520.608398 9.397530 7298.723633" rpy="0.000000 0.000000 22.106977" a="67.893"/>
	<group name="Land_Container_1Mo" pos="14537.462891 9.397530 7294.258301" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Platform1_Block" pos="14563.285156 28.603939 7217.238281" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14563.285156 27.788948 7217.238281" rpy="179.999908 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14555.182617 28.603939 7211.352051" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14555.181641 27.803932 7211.352051" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14547.082031 28.603939 7205.465820" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14547.082031 27.788948 7205.465820" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14538.986328 28.603939 7199.584473" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14538.986328 27.803932 7199.584961" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Wall_IndCnc4_Low_8" pos="14512.085938 7.256485 7316.032715" rpy="0.000000 0.000000 -35.140285" a="125.14"/>
	<group name="StaticObj_Pier_Wooden1_End" pos="14509.470703 -0.712237 7322.121582" rpy="-0.000000 0.000000 -125.139908" a="-144.86"/>
	<group name="StaticObj_Pier_Wooden1_End" pos="14506.172852 -0.710589 7327.252930" rpy="-0.000000 -0.000000 54.859535" a="35.1405"/>
	<group name="StaticObj_Boathouse_PierL" pos="14502.542969 -4.065494 7315.102539" rpy="0.000000 0.000000 -35.140285" a="125.14"/>
	<group name="StaticObj_Boathouse_PierL" pos="14497.127930 -4.065494 7323.297852" rpy="0.000000 0.000000 -35.140289" a="125.14"/>
	<group name="Land_Container_1Mo" pos="14517.902344 11.945044 7298.003906" rpy="0.000000 0.000000 112.538322" a="-22.5383"/>
	<group name="Land_Container_1Mo" pos="14513.068359 9.397530 7304.997070" rpy="0.000000 0.000000 143.429382" a="-53.4294"/>
	<group name="Land_Tisy_RadarPlatform_Top" pos="14504.373047 0.904145 7287.066406" rpy="0.000000 0.000000 -35.000000" a="125"/>
	<group name="StaticObj_Wall_IndCnc4_Low_8" pos="14515.295898 7.256485 7271.403320" rpy="0.000000 0.000000 144.999969" a="-55"/>
	<group name="StaticObj_Pipe_Small_Stairs" pos="14506.013672 8.890602 7304.790039" rpy="0.000000 0.000000 -35.000000" a="125"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14513.054688 8.667770 7294.416016" rpy="0.000000 0.000000 -35.000000" a="125"/>
	<group name="StaticObj_Pipe_Small_Stairs" pos="14520.896484 8.893105 7283.537598" rpy="0.000000 0.000000 -34.999996" a="125"/>
	<group name="Land_Tank_Big" pos="14554.062500 0.873223 7291.876465" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14554.062500 -10.126758 7291.876465" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14554.062500 22.591064 7291.876465" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14554.062500 11.590567 7291.876465" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14503.212891 0.873223 7255.782715" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14503.212891 -10.126758 7255.782715" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14503.212891 22.591064 7255.782715" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14503.212891 11.590567 7255.782715" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14590.397461 0.873223 7241.281738" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14590.397461 -10.126758 7241.281738" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14590.397461 22.591064 7241.281738" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14590.397461 11.590567 7241.281738" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14539.748047 0.873223 7205.379883" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14539.748047 -10.126758 7205.379883" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="Land_Tank_Big" pos="14539.748047 22.591064 7205.379883" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Tank_Big" pos="14539.748047 11.590567 7205.379883" rpy="179.999893 -0.000005 179.999893" a="-89.9999"/>
	<group name="StaticObj_Pipe_Small2_Ground" pos="14503.366211 7.934769 7308.238281" rpy="0.000000 0.000000 144.999969" a="-55"/>
	<group name="StaticObj_Pipe_Small2_High_Ground" pos="14523.682617 3.140381 7279.221680" rpy="0.000000 0.000000 144.999969" a="-55"/>
	<group name="Land_Pipe_Big_Ground1" pos="14507.935547 11.684423 7265.447754" rpy="-0.000000 0.000000 145.574799" a="-55.5748"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14514.638672 11.867384 7256.001953" rpy="-0.000000 0.000000 145.574661" a="-55.5747"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14524.800781 11.867384 7241.163086" rpy="-0.000000 0.000000 145.574661" a="-55.5747"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14534.962891 11.867384 7226.345215" rpy="-0.000000 0.000000 145.574661" a="-55.5747"/>
	<group name="Land_Pipe_Big_CornerL" pos="14542.535156 12.124884 7217.296875" rpy="-0.000000 0.000000 145.574799" a="-55.5748"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14553.243164 11.864882 7223.487793" rpy="-0.000000 0.000000 54.905136" a="35.0949"/>
	<group name="Land_Pipe_Big_CornerL" pos="14575.070313 9.447128 7240.204590" rpy="179.999893 -0.000005 144.905045" a="-54.905"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14568.845703 11.864882 7250.950195" rpy="-0.000000 0.000000 -35.230721" a="125.231"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14558.476563 11.864882 7265.625488" rpy="-0.000000 0.000000 -35.230721" a="125.231"/>
	<group name="StaticObj_Platform1_Block" pos="14595.685547 28.603939 7240.789551" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14595.685547 27.788948 7240.789551" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14587.582031 28.603939 7234.902832" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14587.582031 27.803932 7234.903320" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14579.482422 28.603939 7229.017090" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14579.481445 27.788948 7229.017090" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14571.386719 28.603939 7223.135742" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14571.385742 27.803932 7223.135742" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14557.404297 28.603939 7225.328125" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14557.404297 27.788948 7225.328125" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14549.300781 28.603939 7219.441895" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14549.300781 27.803932 7219.441895" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14541.201172 28.603939 7213.556152" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14541.200195 27.788948 7213.556152" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14533.105469 28.603939 7207.674805" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14533.104492 27.803932 7207.674805" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14589.804688 28.603939 7248.879395" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14589.803711 27.788948 7248.879395" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14581.701172 28.603939 7242.993164" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14581.701172 27.803932 7242.993164" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14573.600586 28.603939 7237.106934" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14573.599609 27.788948 7237.106934" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14565.504883 28.603939 7231.225586" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14565.503906 27.803932 7231.226074" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14551.520508 28.603939 7233.420898" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14551.519531 27.788948 7233.420898" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14543.417969 28.603939 7227.534668" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14543.416992 27.803932 7227.534668" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14535.316406 28.603939 7221.648926" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14535.316406 27.788948 7221.648926" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14527.220703 28.603939 7215.767578" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14527.220703 27.803932 7215.767578" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14583.919922 28.603939 7256.972168" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14583.919922 27.788948 7256.972168" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14575.817383 28.603939 7251.085938" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14575.816406 27.803932 7251.085938" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14567.716797 28.603939 7245.200195" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14567.716797 27.788948 7245.200195" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14559.621094 28.603939 7239.318848" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14559.621094 27.803932 7239.318848" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14545.631836 28.603939 7241.528809" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14545.630859 27.788948 7241.528809" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14537.529297 28.603939 7235.642578" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14537.528320 27.803932 7235.642578" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14529.427734 28.603939 7229.756836" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14529.427734 27.788948 7229.756836" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14521.332031 28.603939 7223.875488" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14521.332031 27.803932 7223.875488" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14578.031250 28.603939 7265.080078" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14578.031250 27.788948 7265.080078" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14569.928711 28.603939 7259.193848" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14569.927734 27.803932 7259.193848" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14561.828125 28.603939 7253.308105" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14561.828125 27.788948 7253.308105" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14553.732422 28.603939 7247.426758" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14553.732422 27.803932 7247.426758" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14539.748047 28.603939 7249.629395" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14539.748047 27.788948 7249.629395" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14531.644531 28.603939 7243.743164" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14531.644531 27.803932 7243.743164" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14523.544922 28.603939 7237.856934" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14523.543945 27.788948 7237.856934" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14515.449219 28.603939 7231.975586" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14515.448242 27.803932 7231.976074" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14572.148438 28.603939 7273.177734" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14572.147461 27.788948 7273.177734" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14564.044922 28.603939 7267.292969" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14564.044922 27.803932 7267.293457" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14555.944336 28.603939 7261.408203" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14555.943359 27.788948 7261.408203" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14547.848633 28.603939 7255.526855" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14547.847656 27.803932 7255.526855" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14533.864258 28.603939 7257.732422" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14533.863281 27.788948 7257.732422" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14525.761719 28.603939 7251.846191" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14525.760742 27.803932 7251.846191" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14517.660156 28.603939 7245.959961" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14517.660156 27.788948 7245.959961" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14509.564453 28.603939 7240.078613" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14509.564453 27.803932 7240.079102" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14566.263672 28.603939 7281.278320" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14566.263672 27.788948 7281.278320" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14558.161133 28.603939 7275.393555" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14558.160156 27.803932 7275.393555" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14550.060547 28.603939 7269.509766" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14550.060547 27.788948 7269.509766" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14541.964844 28.603939 7263.629883" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14541.964844 27.803932 7263.629883" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14527.982422 28.603939 7265.832031" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14527.982422 27.788948 7265.832031" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14519.879883 28.603939 7259.946289" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14519.878906 27.803932 7259.946289" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14511.779297 28.603939 7254.060547" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14511.779297 27.788948 7254.060547" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14503.683594 28.603939 7248.179199" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14503.683594 27.803932 7248.179199" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14560.382813 28.603939 7289.375977" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14560.382813 27.788948 7289.375977" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14552.279297 28.603939 7283.491211" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14552.279297 27.803932 7283.491699" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14544.179688 28.603939 7277.607422" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14544.178711 27.788948 7277.607422" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14536.083984 28.603939 7271.728027" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14536.083008 27.803932 7271.728027" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14522.103516 28.603939 7273.927246" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14522.103516 27.788948 7273.927246" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14514.000977 28.603939 7268.042969" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14514.000000 27.803932 7268.042969" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14505.900391 28.603939 7262.158203" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14505.900391 27.788948 7262.158203" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14497.804688 28.603939 7256.276855" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14497.804688 27.803932 7256.276855" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14554.503906 28.603939 7297.471191" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14554.503906 27.788948 7297.471191" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14546.400391 28.603939 7291.586914" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14546.400391 27.803932 7291.586914" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14538.300781 28.603939 7285.702637" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14538.299805 27.788948 7285.702637" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Platform1_Block" pos="14530.205078 28.603939 7279.823242" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Platform1_Block" pos="14530.204102 27.803932 7279.823242" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14566.128906 11.864882 7232.534668" rpy="-0.000000 0.000000 54.905136" a="35.0949"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14548.107422 11.864882 7280.310059" rpy="-0.000000 0.000000 -35.230721" a="125.231"/>
	<group name="Land_Pipe_Big_Ground2" pos="14541.855469 11.680708 7289.486816" rpy="0.000000 0.000000 -35.140606" a="125.141"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14514.320313 9.729828 7256.534668" rpy="179.999908 -0.000005 -34.425003" a="124.425"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14524.406250 9.729828 7241.723145" rpy="179.999893 -0.000005 -34.425003" a="124.425"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14534.549805 9.729828 7226.910156" rpy="179.999893 -0.000005 -34.425007" a="124.425"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14548.507813 9.652321 7279.740723" rpy="179.999908 -0.000005 144.769287" a="-54.7693"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14558.867188 9.652321 7265.077637" rpy="179.999893 -0.000005 144.769287" a="-54.7693"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14569.222656 9.652321 7250.412598" rpy="179.999893 -0.000005 144.769287" a="-54.7693"/>
	<group name="Land_Pipe_Big_CornerL" pos="14575.112305 12.122145 7240.259277" rpy="0.000000 0.000000 54.429577" a="35.5704"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14552.670898 9.737305 7223.101563" rpy="179.999893 -0.000005 -125.094528" a="-144.905"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14565.556641 9.704811 7232.221191" rpy="179.999893 -0.000005 -125.094528" a="-144.905"/>
	<group name="Land_Pipe_Big_CornerL" pos="14542.392578 9.477287 7217.323730" rpy="179.999893 -0.000005 -124.093018" a="-145.907"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14577.404297 20.439358 7238.890137" rpy="179.999908 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14575.960938 20.439358 7240.873047" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14542.919922 20.439365 7214.699219" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14541.515625 20.439365 7216.710938" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14530.377930 20.439365 7232.958008" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14528.974609 20.439365 7234.969727" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14520.177734 20.439365 7247.934082" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14518.773438 20.439365 7249.945313" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14509.137695 20.441868 7264.064941" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14507.734375 20.441868 7266.076172" rpy="179.999893 -0.000005 145.145630" a="-55.1456"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14564.648438 20.439358 7256.949219" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14563.205078 20.439358 7258.932129" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14554.279297 20.439358 7271.564941" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14552.835938 20.439358 7273.547363" rpy="179.999893 -0.000005 144.000000" a="-54"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14542.936523 20.439358 7287.747559" rpy="179.999893 -0.000005 144.716049" a="-54.716"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14541.517578 20.439358 7289.747559" rpy="179.999893 -0.000005 144.716049" a="-54.716"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14558.501953 20.439373 7227.046387" rpy="179.999893 -0.000005 -125.509201" a="-144.491"/>
	<group name="StaticObj_Pipe_Big_Support" pos="14560.502930 20.439373 7228.471680" rpy="179.999893 -0.000005 -125.509201" a="-144.491"/>
	<group name="Land_Wall_Gate_Tin6_1" pos="14577.417969 14.841160 7240.726074" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="Land_Wall_Gate_Tin6_1" pos="14542.947266 14.766110 7214.973633" rpy="-0.000000 0.000000 143.999893" a="-53.9999"/>
	<group name="Land_Tower_TC2_Mid" pos="14546.476563 -0.298369 7248.515137" rpy="179.999908 -0.000005 179.999908" a="-89.9999"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14530.888672 -0.771167 7268.955566" rpy="0.000000 0.000000 -35.000000" a="125"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14530.894531 -2.056170 7268.973145" rpy="179.999908 -0.000005 144.999969" a="-55"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14542.338867 -0.771167 7252.553223" rpy="0.000000 0.000000 -35.000000" a="125"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14542.345703 -2.056170 7252.570801" rpy="179.999893 -0.000005 144.999969" a="-55"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14552.365234 -0.771167 7281.394531" rpy="0.000000 0.000000 10.119173" a="79.8808"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14552.381836 -2.056170 7281.402344" rpy="179.999893 -0.000005 -169.879684" a="-100.12"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14548.819336 -0.771167 7261.710938" rpy="0.000000 0.000000 10.119173" a="79.8808"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14548.835938 -2.056170 7261.718262" rpy="179.999893 -0.000005 -169.879684" a="-100.12"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14519.177734 -0.771182 7252.158691" rpy="0.000000 0.000000 -81.986343" a="171.986"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14519.169922 -2.056170 7252.174316" rpy="179.999893 -0.000005 98.012672" a="-8.01267"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14538.980469 -0.771182 7249.339844" rpy="0.000000 0.000000 -81.986343" a="171.986"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14538.971680 -2.056170 7249.354980" rpy="179.999893 -0.000005 98.012672" a="-8.01267"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14580.772461 -0.771167 7242.296387" rpy="0.000000 0.000000 99.645798" a="-9.6458"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14580.781250 -2.056170 7242.279297" rpy="179.999893 -0.000005 -80.351929" a="170.352"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14561.060547 -0.771167 7245.679199" rpy="0.000000 0.000000 99.645798" a="-9.6458"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14561.068359 -2.056170 7245.662598" rpy="179.999893 -0.000005 -80.351929" a="170.352"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14542.009766 -0.771182 7218.755371" rpy="0.000000 0.000000 -172.084702" a="-97.9153"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14541.994141 -2.056170 7218.748535" rpy="179.999893 -0.000005 7.912657" a="82.0873"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14544.791992 -0.771182 7238.562988" rpy="0.000000 0.000000 -172.084702" a="-97.9153"/>
	<group name="StaticObj_Pipe_Small_20m" pos="14544.777344 -2.056170 7238.555664" rpy="179.999893 -0.000005 7.912657" a="82.0873"/>
	<group name="Land_Tower_TC3_Red" pos="14553.324219 32.352509 7291.856934" rpy="-0.000000 -0.000000 53.999939" a="36.0001"/>
	<group name="Land_Mil_ControlTower" pos="14499.015625 15.969699 7296.877441" rpy="-0.000000 -0.000000 -124.512733" a="-145.487"/>
	<group name="Land_Guardhouse" pos="14514.175781 9.023621 7273.099609" rpy="-0.000000 0.000000 144.859390" a="-54.8594"/>
	<group name="StaticObj_Wreck_Ship_Big_Lifeboat" pos="14509.902344 3.037552 7326.148438" rpy="179.999893 0.000005 -124.979385" a="-145.021"/>
	<group name="Land_DieselPowerPlant_Tank_Small" pos="14498.166992 36.787964 7254.859863" rpy="-0.000000 0.000000 -25.469206" a="115.469"/>
	<group name="Land_DieselPowerPlant_Tank_Small" pos="14501.939453 36.787964 7249.544922" rpy="-0.000000 0.000000 -26.368580" a="116.369"/>
	<group name="Land_DieselPowerPlant_Building" pos="14540.471680 42.661224 7223.114258" rpy="-0.000000 -0.000000 53.709850" a="36.2901"/>
	<group name="Land_Radio_building" pos="14516.075195 36.726807 7255.840820" rpy="0.000000 0.000000 -125.445000" a="-144.555"/>
	<group name="Land_Construction_Building" pos="14558.518555 39.023788 7264.170898" rpy="-0.000000 0.000000 -125.999924" a="-144"/>
	<group name="Land_Pier_Crane_A" pos="14532.111328 37.414993 7281.341797" rpy="0.000000 0.000000 144.287704" a="-54.2877"/>
	<group name="Land_Pier_Crane_B" pos="14530.595703 50.532455 7286.959961" rpy="0.000000 0.000000 -114.713226" a="-155.287"/>
	<group name="Land_Smokestack_Big" pos="14524.137695 60.904793 7242.520508" rpy="-0.000000 0.000000 -125.477196" a="-144.523"/>
	<group name="Land_Container_1Moh" pos="14555.882813 45.706940 7255.844238" rpy="-0.000000 0.000000 -80.214348" a="170.214"/>
	<group name="Land_Container_1Moh" pos="14556.549805 45.706940 7249.605957" rpy="-0.000000 0.000000 -40.107204" a="130.107"/>
	<group name="Land_Container_1Moh" pos="14575.670898 45.750000 7251.054199" rpy="-0.000000 0.000000 22.918390" a="67.0816"/>
	<group name="Land_Mil_Tent_Big1_1" pos="14565.087891 44.457825 7246.072754" rpy="-0.000000 0.000000 -126.768280" a="-143.232"/>
	<group name="Land_Mil_Tent_Big1_3" pos="14570.328125 44.427734 7257.632813" rpy="-0.000000 0.000000 52.709286" a="37.2907"/>
	<group name="Land_Mil_Tent_Big2_4" pos="14533.526367 34.149536 7258.752441" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="Land_Mil_Tent_Big2_5" pos="14537.625000 34.149536 7252.999512" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="Land_Mil_Tent_Big2_3" pos="14529.222656 34.149536 7264.600098" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="Land_Container_1Aoh" pos="14556.540039 41.694458 7279.429688" rpy="0.000000 0.000000 53.214390" a="36.7856"/>
	<group name="Land_Container_1Bo" pos="14550.083984 41.694458 7269.300293" rpy="0.000000 0.000000 36.025616" a="53.9744"/>
	<group name="Land_Container_1Bo" pos="14580.827148 48.726669 7259.746582" rpy="0.000000 0.000000 -107.214355" a="-162.786"/>
	<group name="Land_Container_1Mo" pos="14558.445313 45.706940 7251.217773" rpy="-0.000000 0.000000 -40.107204" a="130.107"/>
	<group name="Land_Container_1Mo" pos="14557.544922 48.291824 7250.466309" rpy="-0.000000 0.000000 -70.330872" a="160.331"/>
	<group name="Land_Container_1Mo" pos="14564.759766 45.712524 7271.253418" rpy="-0.000000 0.000000 -36.814224" a="126.814"/>
	<group name="Wreck_Mi8" pos="14554.749023 46.391312 7262.093750" rpy="-3.355288 1.196545 -80.214371" a="170.214"/>
	<group name="Land_Container_1Bo" pos="14502.591797 9.418381 7285.041016" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Container_1Aoh" pos="14511.109375 9.406242 7283.299316" rpy="-0.000000 0.000000 -126.051056" a="-143.949"/>
	<group name="Land_Container_1Bo" pos="14509.097656 9.418381 7289.439453" rpy="-0.000000 0.000000 108.862343" a="-18.8623"/>
	<group name="StaticObj_Container_1C" pos="14510.787109 12.029554 7286.017090" rpy="0.000000 0.000000 -6.540798" a="96.5408"/>
	<group name="StaticObj_Container_1D" pos="14504.566406 9.465584 7276.362305" rpy="0.000000 0.000000 -73.647995" a="163.648"/>
	<group name="Land_DieselPowerPlant_Tank_Big" pos="14578.582031 34.903870 7236.797852" rpy="0.000000 0.000000 -45.765873" a="135.766"/>
	<group name="Land_Smokestack_Metal" pos="14586.990234 49.189178 7241.897461" rpy="0.000000 0.000000 -35.999996" a="126"/>
	<group name="Land_Smokestack_Medium" pos="14520.671875 61.564491 7227.409180" rpy="0.000000 0.000000 144.266190" a="-54.2662"/>
	<group name="StaticObj_Container_1C" pos="14554.652344 41.777588 7254.629395" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Container_1C" pos="14570.968750 41.777588 7255.629395" rpy="-0.000000 0.000000 45.836788" a="44.1632"/>
	<group name="StaticObj_Container_1D" pos="14561.755859 41.792068 7264.377930" rpy="0.000000 0.000000 -35.999973" a="126"/>
	<group name="StaticObj_Container_1D" pos="14559.052734 33.777374 7258.677246" rpy="0.000000 0.000000 -51.901478" a="141.901"/>
	<group name="Land_Container_1Bo" pos="14553.653320 37.721283 7255.805176" rpy="0.000000 0.000000 -49.918358" a="139.918"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14588.814453 35.922180 7232.655273" rpy="0.000000 0.000000 53.667820" a="36.3322"/>
	<group name="Land_Pipe_Big_Ground2" pos="14597.908203 35.737457 7239.110352" rpy="0.000000 0.000000 53.667820" a="36.3322"/>
	<group name="Land_Roadblock_Table" pos="14527.817383 8.595467 7290.590332" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Roadblock_Table" pos="14527.316406 8.595467 7287.191406" rpy="-0.000000 0.000000 57.295769" a="32.7042"/>
	<group name="Land_Roadblock_Table" pos="14532.521484 8.595467 7291.790039" rpy="-0.000000 0.000000 74.484489" a="15.5155"/>
	<group name="StaticObj_Roadblock_Bags_Curve" pos="14524.283203 8.716064 7293.173828" rpy="-0.000000 0.000000 122.039536" a="-32.0395"/>
	<group name="StaticObj_Roadblock_Bags_EndL" pos="14521.471680 8.644760 7292.883301" rpy="-0.000000 0.000000 63.025299" a="26.9747"/>
	<group name="StaticObj_Roadblock_Bags_Long" pos="14527.113281 8.032448 7294.688965" rpy="-0.000000 0.000000 51.566154" a="38.4338"/>
	<group name="StaticObj_Roadblock_Bags_EndR" pos="14525.125000 8.216698 7290.670410" rpy="-0.000000 0.000000 -171.312180" a="-98.6878"/>
	<group name="Land_Roadblock_Table" pos="14511.888672 8.607277 7272.620117" rpy="-0.000000 0.000000 -35.380108" a="125.38"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14508.097656 8.482887 7283.627441" rpy="0.000000 0.000000 144.812836" a="-54.8128"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14509.341797 8.487885 7283.995117" rpy="-0.000000 0.000000 54.287415" a="35.7126"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14508.544922 9.115387 7283.430664" rpy="-0.000000 0.000000 54.287415" a="35.7126"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14535.832031 8.522629 7293.567383" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14535.751953 8.522629 7295.020508" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14535.802734 9.212631 7294.245605" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14534.953125 8.522629 7294.458496" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14512.730469 8.490387 7298.650879" rpy="0.000000 0.000000 57.437634" a="32.5624"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14513.194336 8.490387 7300.167969" rpy="-0.000000 0.000000 3.437743" a="86.5623"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14512.916016 9.090393 7299.183594" rpy="-0.000000 0.000000 3.437743" a="86.5623"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14512.470703 8.613213 7306.024414" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14515.373047 8.610710 7298.826172" rpy="-0.000000 0.000000 3.151339" a="86.8487"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14515.310547 8.610710 7297.386719" rpy="-0.000000 0.000000 3.151339" a="86.8487"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14515.310547 9.240707 7298.086426" rpy="-0.000000 0.000000 3.151339" a="86.8487"/>
	<group name="StaticObj_ammoboxes_stacked" pos="14521.217773 9.094818 7300.254395" rpy="-0.000000 -0.000000 21.891239" a="68.1088"/>
	<group name="StaticObj_ammoboxes_single" pos="14520.648438 8.807327 7298.875488" rpy="-0.000000 0.000000 22.632168" a="67.3678"/>
	<group name="StaticObj_ammoboxes_single" pos="14520.648438 9.207260 7298.875488" rpy="-0.000000 0.000000 22.632168" a="67.3678"/>
	<group name="StaticObj_Garbage_Pile7" pos="14510.636719 8.755592 7282.997070" rpy="0.000000 0.000000 158.845200" a="-68.8452"/>
	<group name="StaticObj_Garbage_Pile8" pos="14511.560547 8.815536 7283.920898" rpy="0.000000 0.000000 -42.899380" a="132.899"/>
	<group name="StaticObj_Garbage_Pile5" pos="14509.621094 8.594971 7289.273438" rpy="-0.000000 -0.000000 23.132368" a="66.8676"/>
	<group name="StaticObj_Garbage_Pile5" pos="14507.685547 8.594971 7290.008301" rpy="-0.000000 -0.000000 -174.004135" a="-95.9959"/>
	<group name="StaticObj_Garbage_Ground_6m_NoLC" pos="14515.486328 8.232361 7311.192383" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Garbage_GroundSq_5m_NoLC" pos="14519.586914 8.252182 7305.340820" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Garbage_GroundSq_5m_NoLC" pos="14529.396484 8.252182 7290.144531" rpy="-0.000000 0.000000 63.025299" a="26.9747"/>
	<group name="StaticObj_Garbage_GroundSq_5m_NoLC" pos="14506.910156 8.217140 7285.355469" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Garbage_Ground_6m_NoLC" pos="14521.425781 8.230652 7306.382813" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14599.211914 32.573914 7237.304688" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14592.747070 32.573914 7232.609375" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14586.294922 32.573914 7227.916504" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14579.841797 32.573914 7223.226563" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14573.376953 32.573914 7218.531250" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14566.923828 32.573914 7213.838379" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14560.464844 32.573914 7209.140625" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14554.000000 32.573914 7204.445313" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14547.546875 32.573914 7199.752441" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14541.083984 32.573914 7195.057129" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14595.525391 32.573914 7249.317871" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14600.212891 32.573914 7242.849609" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14558.018555 32.573914 7301.009766" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14562.707031 32.573914 7294.541016" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14567.394531 32.573914 7288.083984" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14572.078125 32.573914 7281.627930" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14576.763672 32.573914 7275.158691" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14581.455078 32.573914 7268.705078" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14586.145508 32.573914 7262.240723" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14590.833984 32.573914 7255.771973" rpy="0.000000 0.000000 -125.953110" a="-144.047"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14497.970703 32.573914 7247.746094" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14493.277344 32.573914 7254.211914" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14535.525391 32.573914 7196.078613" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14530.830078 32.573914 7202.543945" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14526.137695 32.573914 7208.995605" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14521.449219 32.573914 7215.449707" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14516.757813 32.573914 7221.917969" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14512.054688 32.573914 7228.369629" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14507.361328 32.573914 7234.830078" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14502.666992 32.573914 7241.294922" rpy="0.000000 0.000000 53.994942" a="36.0051"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14494.285156 32.573883 7259.830566" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14500.753906 32.573883 7264.519043" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14507.211914 32.573883 7269.204590" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14513.667969 32.573883 7273.887207" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14523.326172 32.573883 7280.901367" rpy="0.000000 0.000000 -36.001823" a="126.002"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14526.592773 32.573883 7283.261230" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14533.058594 32.573883 7287.951660" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14539.527344 32.573883 7292.639160" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14545.984375 32.573883 7297.325195" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="StaticObj_Wall_Fen4_8" pos="14552.451172 32.573883 7302.014160" rpy="0.000000 0.000000 144.049973" a="-54.05"/>
	<group name="Land_Container_1Aoh" pos="14595.046875 33.201752 7242.875000" rpy="-0.000000 0.000000 53.714794" a="36.2852"/>
	<group name="Land_Container_1Bo" pos="14590.267578 33.230835 7246.144043" rpy="0.000000 0.000000 -35.999996" a="126"/>
	<group name="Land_Container_1Aoh" pos="14557.515625 33.167450 7241.912598" rpy="0.000000 0.000000 -35.856720" a="125.857"/>
	<group name="Land_Container_1Moh" pos="14541.324219 33.214050 7246.404297" rpy="0.000000 0.000000 -71.999947" a="162"/>
	<group name="StaticObj_Container_2E" pos="14495.181641 10.787481 7284.841797" rpy="0.000000 0.000000 -35.999996" a="126"/>
	<group name="StaticObj_Container_2D" pos="14497.569336 10.783361 7287.258789" rpy="0.000000 0.000000 -18.429720" a="108.43"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14500.305664 8.633171 7303.605469" rpy="-0.000000 -0.000000 55.002670" a="34.9973"/>
	<group name="Land_Roadblock_Table" pos="14528.257813 8.734993 7283.218262" rpy="0.000000 0.000000 -9.000000" a="99"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14540.221680 32.419281 7247.090332" rpy="-0.000000 -0.000000 18.000000" a="72"/>
	<group name="StaticObj_Misc_WoodenCrate_3x" pos="14541.423828 32.829544 7246.438477" rpy="-0.000000 0.000000 -158.563904" a="-111.436"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14541.402344 32.294342 7248.647461" rpy="0.000000 0.000000 -22.892969" a="112.893"/>
	<group name="Land_Mil_Guardhouse1" pos="14517.410156 34.196564 7269.136230" rpy="0.000000 0.000000 -125.524803" a="-144.475"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14513.027344 33.339386 7264.145020" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14513.444336 35.640076 7263.283203" rpy="0.000000 0.000000 -156.321198" a="-113.679"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14512.669922 35.625076 7269.381836" rpy="0.000000 0.000000 -35.999996" a="126"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14511.432617 35.640076 7261.115234" rpy="0.000000 0.000000 -124.378548" a="-145.621"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14510.292969 35.640076 7260.304688" rpy="0.000000 0.000000 -125.094719" a="-144.905"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14510.363281 35.640076 7261.332520" rpy="0.000000 0.000000 -124.951477" a="-145.049"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14510.947266 36.267548 7260.762207" rpy="0.000000 0.000000 -124.951477" a="-145.049"/>
	<group name="StaticObj_Misc_Obstacle_Bridge" pos="14514.261719 35.474487 7265.808594" rpy="-0.000000 -0.000000 53.999996" a="36"/>
	<group name="StaticObj_Misc_Obstacle_Bridge" pos="14514.494141 35.474487 7265.485840" rpy="-0.000000 -0.000000 53.999996" a="36"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14513.291992 36.236465 7271.577637" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14514.500000 36.208984 7272.370117" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14516.230469 35.533539 7273.256348" rpy="0.000000 0.000000 -123.257713" a="-146.742"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14518.131836 35.533554 7272.956543" rpy="0.000000 0.000000 -48.772938" a="138.773"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14518.009766 35.533554 7266.100586" rpy="0.000000 0.000000 -125.693291" a="-144.307"/>
	<group name="StaticObj_Misc_WoodPile2" pos="14500.646484 8.503220 7294.967773" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="StaticObj_Misc_WoodPile2" pos="14501.574219 8.503220 7295.623047" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="StaticObj_Misc_WoodPile2" pos="14501.132813 8.503220 7295.310059" rpy="179.999939 -0.000005 -125.999992" a="-144"/>
	<group name="Land_Roadblock_Table" pos="14518.717773 36.534790 7260.641602" rpy="-0.000000 -0.000000 54.859428" a="35.1406"/>
	<group name="Land_Roadblock_Table" pos="14523.513672 36.525543 7251.163574" rpy="-0.000000 0.000000 -87.540764" a="177.541"/>
	<group name="StaticObj_Misc_Table_Camp" pos="14517.912109 36.537933 7255.306641" rpy="179.999969 90.000000 179.999969" a="-90"/>
	<group name="StaticObj_Misc_Table_Camp" pos="14492.897461 8.741280 7299.482422" rpy="-0.000091 90.000000 -63.025322" a="153.025"/>
	<group name="Land_Ladder" pos="14537.917969 41.030060 7235.117188" rpy="-0.000000 0.000000 143.999893" a="-53.9999"/>
	<group name="Land_Container_1Moh" pos="14536.004883 39.430496 7241.034668" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="Land_Roadblock_Table" pos="14540.626953 38.611404 7239.169434" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="StaticObj_Pipe_Small2_Ground" pos="14495.369141 31.507725 7258.222656" rpy="-0.000000 0.000000 143.999893" a="-53.9999"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14539.240234 38.502380 7240.958984" rpy="0.000000 0.000000 -40.106983" a="130.107"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14525.736328 32.950256 7272.784180" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14524.034180 32.950256 7274.483887" rpy="-0.000000 0.000000 -85.943451" a="175.943"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14524.195313 32.313828 7272.741699" rpy="0.000000 0.000000 -35.999996" a="126"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14525.479492 32.313812 7274.260742" rpy="0.000000 0.000000 -15.516803" a="105.517"/>
	<group name="StaticObj_Container_2D" pos="14540.840820 34.596603 7275.469727" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="Land_Container_1Aoh" pos="14539.474609 33.233185 7277.525879" rpy="-0.000000 -0.000000 53.999996" a="36"/>
	<group name="Land_Container_1Bo" pos="14541.651367 33.213135 7288.142090" rpy="-0.000000 -0.000000 9.000000" a="81"/>
	<group name="StaticObj_Garbage_Container2_Open" pos="14530.916016 8.924606 7286.465820" rpy="0.000000 0.000000 -27.000000" a="117"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14575.556641 45.438324 7259.888184" rpy="0.000000 0.000000 -34.162060" a="124.162"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14541.091797 32.953659 7244.283203" rpy="-0.000000 0.000000 15.899641" a="74.1004"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14547.663086 40.723923 7269.540527" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14549.264648 40.723938 7279.435547" rpy="-0.000000 0.000000 52.138992" a="37.861"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14559.671875 44.673889 7277.210938" rpy="-0.000000 0.000000 97.975571" a="-7.97557"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14565.578125 44.673889 7261.513672" rpy="-0.000000 0.000000 138.082382" a="-48.0824"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14554.487305 40.729370 7279.992676" rpy="-0.000000 0.000000 53.571281" a="36.4287"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14554.487305 41.354309 7279.992676" rpy="-0.000000 0.000000 53.571281" a="36.4287"/>
	<group name="StaticObj_Misc_WoodenCrate" pos="14554.038086 40.729370 7280.645020" rpy="-0.000000 0.000000 53.571281" a="36.4287"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14557.272461 40.798874 7261.941895" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14565.521484 40.798889 7258.179688" rpy="-0.000000 0.000000 -28.647816" a="118.648"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14558.615234 40.798889 7255.279297" rpy="-0.000000 0.000000 57.295837" a="32.7042"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14563.434570 40.798889 7246.106445" rpy="-0.000000 0.000000 57.295837" a="32.7042"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14564.935547 40.798859 7245.496094" rpy="-0.000000 0.000000 -5.586304" a="95.5863"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14563.518555 41.397537 7244.779785" rpy="-0.000000 0.000000 -34.377346" a="124.377"/>
	<group name="Land_Container_1Moh" pos="14564.792969 41.714813 7251.265625" rpy="-0.000000 0.000000 -41.682487" a="131.682"/>
	<group name="Land_Roadblock_Table" pos="14548.769531 40.895142 7259.289063" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="Land_Roadblock_Table" pos="14557.578125 40.895142 7267.588379" rpy="-0.000000 -0.000000 111.295639" a="-21.2956"/>
	<group name="Land_Roadblock_Table" pos="14566.787109 44.807907 7262.789551" rpy="-0.000000 -0.000000 53.999985" a="36"/>
	<group name="StaticObj_Misc_Table_Camp" pos="14568.501953 44.892792 7267.077637" rpy="179.999939 -0.000005 179.999939" a="-89.9999"/>
	<group name="Land_Roadblock_Table" pos="14572.280273 44.877167 7251.703613" rpy="-0.000000 0.000000 -45.836617" a="135.837"/>
	<group name="Land_Roadblock_Table" pos="14559.632813 44.810516 7252.286133" rpy="-0.000000 -0.000000 49.272987" a="40.727"/>
	<group name="StaticObj_Misc_Table_Camp" pos="14565.140625 44.755203 7252.575195" rpy="179.999969 90.000000 179.999969" a="-90"/>
	<group name="StaticObj_ammoboxes_stacked" pos="14565.361328 45.406677 7270.432129" rpy="0.000000 0.000000 -37.432343" a="127.432"/>
	<group name="StaticObj_ammoboxes_stacked" pos="14564.244141 45.406677 7271.921875" rpy="0.000000 0.000000 -37.432343" a="127.432"/>
	<group name="StaticObj_ammoboxes_stacked" pos="14554.117188 45.399170 7256.173340" rpy="0.000000 0.000000 -80.404167" a="170.404"/>
	<group name="StaticObj_ammoboxes_single" pos="14555.486328 45.114731 7255.933105" rpy="0.000000 0.000000 -80.331795" a="170.332"/>
	<group name="StaticObj_ammoboxes_single" pos="14555.486328 45.507233 7255.933105" rpy="0.000000 0.000000 -80.331795" a="170.332"/>
	<group name="StaticObj_ammoboxes_single" pos="14556.412109 45.114731 7255.772949" rpy="0.000000 0.000000 -80.331795" a="170.332"/>
	<group name="StaticObj_ammoboxes_single" pos="14556.412109 45.507233 7255.772949" rpy="0.000000 0.000000 -80.331795" a="170.332"/>
	<group name="StaticObj_ammoboxes_single" pos="14561.421875 45.894516 7254.028320" rpy="0.000000 0.000000 -32.489635" a="122.49"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14557.135742 44.920334 7248.328613" rpy="-0.000000 0.000000 -10.886376" a="100.886"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14555.105469 45.570099 7250.985840" rpy="-0.000000 0.000000 52.425312" a="37.5747"/>
	<group name="StaticObj_Misc_WoodenCrate_3x" pos="14556.096680 45.315521 7249.549316" rpy="-0.000000 -0.000000 48.867329" a="41.1327"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14558.078125 44.920334 7250.641113" rpy="-0.000000 0.000000 -40.107037" a="130.107"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14557.230469 44.920334 7251.655762" rpy="-0.000000 0.000000 -40.107044" a="130.107"/>
	<group name="Land_Roadblock_WoodenCrate" pos="14558.291016 44.920334 7251.678223" rpy="-0.000000 0.000000 -40.107044" a="130.107"/>
	<group name="StaticObj_Misc_WoodenCrate_5x" pos="14566.474609 41.397537 7252.754883" rpy="-0.000000 0.000000 -38.388100" a="128.388"/>
	<group name="StaticObj_Misc_WoodenCrate_3x" pos="14556.096680 41.192932 7249.549316" rpy="-0.000000 -0.000000 48.867329" a="41.1327"/>
	<group name="StaticObj_Pipe_Big_18m" pos="14574.322266 35.922180 7221.997070" rpy="0.000000 0.000000 53.667820" a="36.3322"/>
	<group name="Land_Pipe_Big_Ground1" pos="14565.093750 35.740952 7214.997070" rpy="-0.000000 -0.000000 53.999863" a="36.0001"/>
	<group name="StaticObj_Power_TransformerStation_Big" pos="14511.197266 35.244537 7240.607910" rpy="-0.000000 0.000000 -36.475399" a="126.475"/>
	<group name="Land_Sawmill_Illuminanttower" pos="14500.269531 41.815308 7262.563965" rpy="-0.000000 -0.000000 143.524933" a="-53.5249"/>
	<group name="Land_Sawmill_Illuminanttower" pos="14561.298828 41.815308 7211.573242" rpy="-0.000000 -0.000000 -35.849422" a="125.849"/>
	<group name="Land_Sawmill_Illuminanttower" pos="14515.443359 18.029293 7281.822266" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Road_Sidewalk_Stairs" pos="14518.091797 30.092361 7279.940430" rpy="0.000000 0.000000 -35.999981" a="126"/>
	<group name="StaticObj_Road_Sidewalk_Stairs" pos="14517.208984 30.114868 7279.327637" rpy="0.000000 0.000000 -35.999977" a="126"/>
	<group name="StaticObj_Road_Sidewalk_Stairs" pos="14516.337891 30.134857 7278.719727" rpy="0.000000 0.000000 -35.999996" a="126"/>
	<group name="StaticObj_Wall_PipeFence_8" pos="14517.986328 30.449879 7280.866699" rpy="-39.999992 0.000000 53.819622" a="36.1804"/>
	<group name="StaticObj_Wall_PipeFence_8" pos="14515.537109 30.449879 7279.057617" rpy="-39.999992 0.000000 53.819622" a="36.1804"/>
	<group name="StaticObj_Wall_IndCnc4_Low_Pole" pos="14519.701172 33.056778 7278.533203" rpy="-0.000000 0.000000 -36.094395" a="126.094"/>
	<group name="StaticObj_Wall_IndCnc4_Low_Pole" pos="14517.015625 33.056778 7276.603516" rpy="-0.000000 0.000000 -36.094387" a="126.094"/>
	<group name="Land_Guardhouse" pos="14514.912109 9.515434 7314.125977" rpy="-0.000000 -0.000000 54.716263" a="35.2837"/>
	<group name="Land_Tower_TC2_Base" pos="14561.997070 54.661316 7227.276855" rpy="-0.000000 0.000000 -127.912773" a="-142.087"/>
	<group name="Land_Tower_TC2_Mid" pos="14562.670898 104.240829 7227.129395" rpy="-0.000000 0.000000 -127.768806" a="-142.231"/>
	<group name="Land_Tower_TC2_Top" pos="14563.066406 153.977066 7227.327148" rpy="-0.000000 0.000000 -127.768806" a="-142.231"/>
	<group name="Land_DieselPowerPlant_Tank_Small" pos="14578.796875 43.197876 7236.423828" rpy="-0.000000 0.000000 -25.469206" a="115.469"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14531.059570 8.674927 7291.229004" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_Chair_Camp2" pos="14528.593750 8.462585 7291.913574" rpy="90.000000 0.000000 97.403168" a="-7.40317"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14527.139648 8.667244 7285.762207" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_Chair_Camp2" pos="14492.044922 8.786118 7301.281738" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14528.238281 8.811958 7283.985840" rpy="-0.000000 -0.000000 18.000000" a="72"/>
	<group name="StaticObj_Misc_Chair_Camp2" pos="14512.242188 8.405632 7271.625488" rpy="179.999954 44.000004 179.999954" a="-90"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14517.503906 36.617859 7260.420410" rpy="-0.000000 0.000000 0.000000" a="90"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14518.001953 36.405457 7253.920410" rpy="-90.000000 0.000000 -108.861984" a="-161.138"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14522.908203 36.617859 7251.720215" rpy="-0.000000 0.000000 -126.051109" a="-143.949"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14560.667969 44.867722 7252.489746" rpy="-0.000000 0.000000 39.142475" a="50.8575"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14565.272461 44.570404 7253.990234" rpy="-90.000000 0.000000 39.142506" a="50.8575"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14567.074219 44.570404 7264.391113" rpy="-90.000000 0.000000 39.142506" a="50.8575"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14568.875977 44.967743 7265.790527" rpy="-0.000000 -0.000000 39.142506" a="50.8575"/>
	<group name="StaticObj_Misc_Chair_Camp1" pos="14572.282227 45.488052 7251.785645" rpy="179.999939 46.299793 -137.276993" a="-132.723"/>
	
Save your changes & upload if you need to.

Restart your server and the new structures will appear immediatly, and then they will slowly stock with loot. If you do a wipe will start to appear immediatly.

At the time of uploading these files you cannot spawn infected zombies over water, so you can't add infected to these locations.

Org File Created by XMC.

If you upload this to another Discord or webpage, please leave filename intact and dont take credit
as your own. Thank you and enjoy :)  

Thanks, Rob.



